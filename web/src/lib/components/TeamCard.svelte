<script lang="ts">
import type { TeamWithRelations } from "$lib/types";
import { formattedDate } from "$lib/utils/dates";

let { team }: { team: TeamWithRelations } = $props();
</script>

<a href={`/teams/${team.team.id}`} class="card hover-card">
  <h3 class="text-xl font-bold">{team.team.name}</h3>
  <div class="flex flex-col gap-1">
      <span class="text-sm text-gray-400 font-mono">
        {team.stored_keys?.length} managed {`${team.stored_keys?.length === 1 ? "key" : "keys"}`}
      </span>
      <span class="text-sm text-gray-400 font-mono">
          {team.team_users?.length} {`${team.team_users?.length === 1 ? "member" : "members"}`}
      </span>
  </div>
  <span class="text-xs text-gray-500">Created: {formattedDate(new Date(team.team.created_at))}</span>
  
</a>
