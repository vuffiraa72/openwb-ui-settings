<template>
	<nav class="navbar navbar-expand-lg bg-dark navbar-dark fixed-top">
		<a class="navbar-brand" href="/openWB/web/">
			<span>openWB</span>
		</a>
		<button
			class="navbar-toggler"
			type="button"
			data-toggle="collapse"
			data-target="#collapsibleNavbar"
			ref="navbarButton"
		>
			<span class="navbar-toggler-icon"></span>
		</button>
		<div
			class="collapse navbar-collapse"
			id="collapsibleNavbar"
			ref="collapsibleNavbar"
		>
			<ul class="navbar-nav">
				<li class="nav-item">
					<router-link
						to="/Status"
						class="nav-link"
						active-class="active disabled"
					>
						Status
					</router-link>
				</li>
				<li class="nav-item dropdown nav-separator-after">
					<a
						class="nav-link dropdown-toggle"
						href="#"
						role="button"
						data-toggle="dropdown"
						aria-expanded="false"
					>
						Auswertungen
					</a>
					<div class="dropdown-menu" aria-labelledby="navbarDropdown">
						<router-link
							to="/Logging/ChargeLog"
							class="dropdown-item"
							active-class="active disabled"
						>
							Ladeprotokoll
						</router-link>
						<router-link
							to="/Logging/DailyChart"
							class="dropdown-item"
							active-class="active disabled"
						>
							Tagesauswertung
						</router-link>
						<router-link
							to="/Logging/MonthlyChart"
							class="dropdown-item"
							active-class="active disabled"
						>
							Monatsauswertung
						</router-link>
					</div>
				</li>
				<li class="nav-item dropdown">
					<a
						class="nav-link dropdown-toggle"
						href="#"
						role="button"
						data-toggle="dropdown"
						aria-expanded="false"
					>
						Einstellungen
					</a>
					<div class="dropdown-menu" aria-labelledby="navbarDropdown">
						<router-link
							to="/GeneralConfig"
							class="dropdown-item"
							active-class="active disabled"
						>
							Allgemein
						</router-link>
						<router-link
							to="/OptionalComponents"
							class="dropdown-item"
							active-class="active disabled"
						>
							Optionale Komponenten
						</router-link>
					</div>
				</li>
				<li class="nav-item dropdown">
					<a
						class="nav-link dropdown-toggle"
						href="#"
						role="button"
						data-toggle="dropdown"
						aria-expanded="false"
					>
						Ladeeinstellungen
					</a>
					<div class="dropdown-menu" aria-labelledby="navbarDropdown">
						<router-link
							to="/GeneralChargeConfig"
							class="dropdown-item"
							active-class="active disabled"
						>
							Übergreifendes
						</router-link>
						<router-link
							to="/InstantChargeConfig"
							class="dropdown-item"
							active-class="active disabled"
						>
							Sofortladen
						</router-link>
						<router-link
							to="/PVChargeConfig"
							class="dropdown-item"
							active-class="active disabled"
						>
							PV-Laden
						</router-link>
						<router-link
							to="/TimeChargeConfig"
							class="dropdown-item"
							active-class="active disabled"
						>
							Zeitladen
						</router-link>
						<router-link
							to="/ScheduledChargeConfig"
							class="dropdown-item"
							active-class="active disabled"
						>
							Zielladen
						</router-link>
						<router-link
							to="/StandbyChargeConfig"
							class="dropdown-item"
							active-class="active disabled"
						>
							Standby
						</router-link>
					</div>
				</li>
				<li class="nav-item dropdown">
					<a
						class="nav-link dropdown-toggle"
						href="#"
						role="button"
						data-toggle="dropdown"
						aria-expanded="false"
					>
						Konfiguration
					</a>
					<div class="dropdown-menu" aria-labelledby="navbarDropdown">
						<router-link
							to="/HardwareInstallation"
							class="dropdown-item"
							active-class="active disabled"
						>
							Geräte und Komponenten
						</router-link>
						<router-link
							to="/LoadManagementConfiguration"
							class="dropdown-item"
							active-class="active disabled"
						>
							Lastmanagement
						</router-link>
						<router-link
							to="/ChargePointInstallation"
							class="dropdown-item"
							active-class="active disabled"
						>
							Ladepunkte
						</router-link>
						<router-link
							to="/VehicleConfiguration"
							class="dropdown-item"
							active-class="active disabled"
						>
							Fahrzeuge
						</router-link>
					</div>
				</li>
				<li class="nav-item dropdown">
					<a
						class="nav-link dropdown-toggle"
						href="#"
						role="button"
						data-toggle="dropdown"
						aria-expanded="false"
					>
						System
					</a>
					<div class="dropdown-menu" aria-labelledby="navbarDropdown">
						<router-link
							to="/System/CloudConfiguration"
							class="dropdown-item"
							active-class="active disabled"
						>
							Cloud
						</router-link>
						<router-link
							to="/System/MqttBridgeConfiguration"
							class="dropdown-item"
							active-class="active disabled"
						>
							MQTT-Brücken
						</router-link>
						<router-link
							to="/System/DebugConfiguration"
							class="dropdown-item"
							active-class="active disabled"
						>
							Fehlersuche
						</router-link>
						<router-link
							to="/System/Support"
							class="dropdown-item"
							active-class="active disabled"
						>
							Support
						</router-link>
						<router-link
							to="/System/DataProtection"
							class="dropdown-item"
							active-class="active disabled"
						>
							Datenschutz
						</router-link>
						<router-link
							to="/System/SystemConfiguration"
							class="dropdown-item"
							active-class="active disabled"
						>
							System
						</router-link>
					</div>
				</li>
				<li
					v-if="nodeEnv !== 'production'"
					class="nav-item dropdown nav-separator-before"
				>
					<a
						class="nav-link dropdown-toggle"
						href="#"
						role="button"
						data-toggle="dropdown"
						aria-expanded="false"
					>
						Beispiele
					</a>
					<div class="dropdown-menu" aria-labelledby="navbarDropdown">
						<router-link
							to="/TestingStore"
							class="dropdown-item"
							active-class="active disabled"
						>
							VUEX Store
						</router-link>
					</div>
				</li>
				<li class="nav-item nav-separator-before">
					<a
						class="nav-link"
						href="https://github.com/openWB/core/wiki"
						target="_blank"
					>
						Wiki
						<font-awesome-icon
							fixed-width
							:icon="['fas', 'external-link-alt']"
						/>
					</a>
				</li>
			</ul>
		</div>
	</nav>
</template>

<script>
import { library } from "@fortawesome/fontawesome-svg-core";
import { faExternalLinkAlt as fasExternalLinkAlt } from "@fortawesome/free-solid-svg-icons";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

library.add(fasExternalLinkAlt);

export default {
	name: "OpenwbNavBar",
	components: {
		FontAwesomeIcon,
	},
	computed: {
		nodeEnv() {
			return this.$root.nodeEnv;
		},
	},
	watch: {
		$route() {
			// imitate bootstraps close behavior
			this.$refs["collapsibleNavbar"].classList.remove("show");
			this.$refs["navbarButton"].classList.add("collapsed");
			this.$refs["navbarButton"].setAttribute("aria-expanded", false);
		},
	},
};
</script>

<style scoped>
.nav-item.nav-separator-before {
	border-left: 1px solid rgba(255, 255, 255, 0.5);
	margin-left: 5px;
	padding-left: 5px;
}

.nav-item.nav-separator-after {
	border-right: 1px solid rgba(255, 255, 255, 0.5);
	margin-right: 5px;
	padding-right: 5px;
}

@media (max-width: 992px) {
	.nav-item.nav-separator-before {
		border-left: none;
		margin-left: 0px;
		padding-left: 0px;
		border-top: 1px solid rgba(255, 255, 255, 0.5);
		margin-top: 5px;
		padding-top: 5px;
	}

	.nav-item.nav-separator-after {
		border-right: none;
		margin-right: 0px;
		padding-right: 0px;
		border-bottom: 1px solid rgba(255, 255, 255, 0.5);
		margin-bottom: 5px;
		padding-bottom: 5px;
	}
}
</style>
