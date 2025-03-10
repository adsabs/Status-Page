<script lang="ts">
	import type { ReportFile } from '$lib/types';
	import moment from 'moment';

	export let incidents: ReportFile['incidents'];
</script>

<div class="">
	<h1 class="text-2xl font-bold text-left">Recent incidents</h1>
	<ul class="timeline timeline-vertical mt-4 lg:mt10">
		{#each incidents as incident, i}
			<li>
				{#if i > 0}
					<hr class:bg-blue-500={incident.open} />
				{/if}
				<div class="timeline-start">{moment.unix(incident.date).format('MMM Do YY HH:MM')}</div>
				<div class="timeline-middle" class:text-primary={incident.open}>
					{#if incident.open}
						<div class="badge badge-primary bg-blue-500 border-0">⤫</div>
					{:else}
						<div class="badge">✓</div>
					{/if}
				</div>
				<div class="timeline-end timeline-box">
					<a href={incident.url} target="_blank">{incident.title}</a>
				</div>

				{#if i < incidents.length - 1}
					<hr class:bg-blue-500={incident.open} />
				{/if}
			</li>
		{/each}
	</ul>
</div>
