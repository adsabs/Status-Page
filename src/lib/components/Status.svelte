<script lang="ts">
	import { StatusCode, type Status } from '$lib/types';

	export let name: string;
	export let statuses: Status[];

	const calculateDifferenceInDays = (firstDate: Date, secondDate: Date): number =>
		Math.ceil(Math.abs(+firstDate - +secondDate) / (1000 * 60 * 60 * 24)) + 1;

	const calculateDaysFromNow = (date: Date): number =>
		Math.floor(Math.abs(+date - new Date()) / (1000 * 60 * 60 * 24));

	let message = 'Lacking historical data';
	let leftTick = '';
	let rightTick = '';
	let lastStatus: Status = { status: StatusCode.ERROR, date: new Date() };
	if (statuses.length > 0) {
		lastStatus = statuses[statuses.length - 1];
		const operationPercentage = Math.floor(
			(statuses.reduce((prev, current) => prev + (current.status === StatusCode.OK ? 1 : 0), 0) /
				statuses.length) *
				100
		);

		message = `Operation in last ${calculateDifferenceInDays(statuses[0].date, lastStatus.date)} days: ${operationPercentage}%`;
		const diffLeft = calculateDaysFromNow(statuses[0].date);
		const diffRight = calculateDaysFromNow(lastStatus.date);
		leftTick = diffLeft === 0 ? 'Today' : `${diffLeft} days ago`;
		rightTick = diffRight === 0 ? 'Today' : `${diffRight} days ago`;
	}
</script>

<div class="my-8">
	<div class="flex justify-between flex-col md:flex-row">
		<div class="flex items-center gap-3">
			<div
				class="badge text-gray-800"
				class:bg-lime-500={lastStatus.status === StatusCode.OK}
				class:bg-orange-500={lastStatus.status === StatusCode.ERROR}
				class:bg-yellow-400={lastStatus.status === StatusCode.UNSTABLE}
			>
				{lastStatus.status === StatusCode.OK
					? '✓'
					: lastStatus.status === StatusCode.ERROR
						? '⤫'
						: '?'}
			</div>
			<h1 class="text-xl font-bold">{name}</h1>
		</div>
		<p class="text-neutral-500 text-sm text-right">
			{message}
		</p>
	</div>

	<div class="flex mt-2">
		{#each statuses as { status, date }}
			<div
				data-tip={date.toLocaleDateString('en-US', {
					month: 'long',
					day: '2-digit',
					year: 'numeric',
					hour: '2-digit',
					minute: '2-digit'
				})}
				class:bg-lime-500={status === StatusCode.OK}
				class:bg-yellow-400={status === StatusCode.UNSTABLE}
				class:bg-orange-500={status === StatusCode.ERROR}
				class="tooltip ml-0.5 sm:rounded-lg flex-1 h-8 transition ease-in-out delay-150 hover:-translate-y-1"
			></div>
		{/each}
	</div>

	<div class="flex justify-between flex-col md:flex-row text-sm mt-2">
		<p>{leftTick}</p>
		<p class="text-right">{rightTick}</p>
	</div>
</div>
