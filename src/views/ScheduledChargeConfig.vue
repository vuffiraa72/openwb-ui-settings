<template>
	<div class="scheduledChargeConfig">
		<form name="scheduledChargeConfigForm">
			<openwb-base-card title="Phasenumschaltung">
				<div v-if="$store.state.mqtt['openWB/general/extern'] === true">
					<openwb-base-alert subtype="info">
						Diese Einstellungen sind nicht verfügbar, solange sich
						diese openWB im Modus "Nur Ladepunkt" befindet.
					</openwb-base-alert>
				</div>
				<div v-else>
					<openwb-base-button-group-input
						title="Anzahl Phasen"
						:buttons="[
							{ buttonValue: 1, text: '1' },
							{ buttonValue: 3, text: 'Maximum' },
							{ buttonValue: 0, text: 'Automatik' },
						]"
						:model-value="
							$store.state.mqtt[
								'openWB/general/chargemode_config/scheduled_charging/phases_to_use'
							]
						"
						@update:model-value="
							updateState(
								'openWB/general/chargemode_config/scheduled_charging/phases_to_use',
								$event
							)
						"
					>
						<template #help>
							Hier kann eingestellt werden, ob Ladevorgänge im
							Modus "Zielladen" mit nur einer Phase oder dem
							möglichen Maximum in Abhängigkeit vom Ladepunkt und
							Fahrzeug durchgeführt werden. Im Modus "Automatik"
							entscheidet die Regelung, welche Einstellung genutzt
							wird, um das Ziel zu erreichen.
						</template>
					</openwb-base-button-group-input>
				</div>
			</openwb-base-card>
			<openwb-base-submit-buttons
				formName="scheduledChargeConfigForm"
				@save="$emit('save')"
				@reset="$emit('reset')"
				@defaults="$emit('defaults')"
			/>
		</form>
	</div>
</template>

<script>
import ComponentStateMixin from "@/components/mixins/ComponentState.vue";

export default {
	name: "OpenwbScheduledChargeConfig",
	mixins: [ComponentStateMixin],
	data() {
		return {
			mqttTopicsToSubscribe: [
				"openWB/general/extern",
				"openWB/general/chargemode_config/scheduled_charging/phases_to_use",
			],
		};
	},
};
</script>
