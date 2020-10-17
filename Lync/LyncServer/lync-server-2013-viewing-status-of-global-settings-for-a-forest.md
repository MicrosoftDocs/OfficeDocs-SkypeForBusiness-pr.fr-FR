---
title: 'Lync Server 2013 : affichage de l’état des paramètres globaux d’une forêt'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7922fe79d97a1fa83fdaa5afbc1eeddee8523e37
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535581"
---
# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a>Afficher l’état des paramètres globaux d’une forêt dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-20_

Les administrateurs doivent consulter les paramètres globaux d’un déploiement de Lync Server 2013 tous les mois. L’objectif consiste à passer en revue les paramètres implémentés par rapport à un ensemble de configurations connues, une configuration de référence pour garantir la validité des paramètres et déterminer si la documentation de référence doit être mise à jour. Les modifications apportées au paramètre global doivent être implémentées par le biais d’un processus de contrôle des modifications qui doit inclure la documentation des nouveaux paramètres.

Les paramètres globaux à examiner sont décrits dans les sections suivantes :

<div>

## <a name="check-general-settings"></a>Vérifier les paramètres généraux

Vérifiez les paramètres généraux, y compris les domaines SIP (Session Initiation Protocol) pris en charge pour Lync Server 2013.

Les informations de domaine SIP peuvent être renvoyées à l’aide de Windows PowerShell et de la cmdlet **Get-CsSipDomain** . Pour renvoyer ces informations, exécutez la `Get-CsSipDomain` commande Windows PowerShell.

Get-CsSipDomain renverra des informations similaires à celles-ci pour tous les domaines SIP autorisés :

Nom d’identité IsDefault

\-------- ---- ---------

fabrikam.com fabrikam.com true

na.fabrikam.com na.fabrikam.com false

Si la propriété IsDefault est définie sur true, le domaine correspondant est votre domaine SIP par défaut. Vous pouvez utiliser l’applet de commande Set-CsSipDomain pour modifier le domaine SIP par défaut de votre organisation. Toutefois, vous ne pouvez pas supprimer simplement le domaine SIP par défaut car cela vous laissera sans domaine par défaut. Si vous souhaitez supprimer le domaine fabrikam.com (comme indiqué dans l’exemple précédent), vous devez d’abord configurer na.fabrikam.com comme domaine par défaut.

</div>

<div>

## <a name="check-meeting-settings"></a>Vérifier les paramètres de réunion

Les paramètres de réunion incluent les définitions des stratégies de réunion et la prise en charge de la participation des utilisateurs anonymes aux réunions.

Les paramètres de configuration de réunion peuvent être récupérés à l’aide de Windows PowerShell et de la cmdlet **Get-CsMeetingConfiguration** . Par exemple, cette commande renvoie des informations sur les paramètres de configuration de réunion globale :

Get-CsMeetingConfiguration – les paramètres de configuration de réunion « globale » peuvent également être configurés au niveau de l’étendue site. Pour cette raison, vous pouvez utiliser la commande suivante, qui retourne des informations sur tous les paramètres de configuration de réunion :

`Get-CsMeetingConfiguration`

La cmdlet **Get-CsMeetingConfiguration** renvoie des informations semblables aux suivantes :

Identity : global

PstnCallersBypassLobby : true

EnableAssignedConferenceType : true

DesignateAsPresenter : Company

AssignedConferenceTypeByDefault : true

AdmitAnonymousUsersByDefault : true

Encore une fois, le dernier élément de la liste, **AdmitAnonymousUsersByDefault**, active ou désactive la possibilité pour les utilisateurs anonymes de participer à des réunions.

Lors de la vérification des paramètres de configuration de réunion, il peut s’avérer utile de comparer les paramètres actuels et les équivalents par défaut. Vous pouvez afficher les paramètres de configuration de réunion par défaut en exécutant la commande suivante :

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

La commande précédente crée une instance en mémoire uniquement des paramètres de configuration de réunion globaux, une instance qui utilise la valeur par défaut pour chaque propriété. Aucun paramètre de configuration de réunion réel n’est créé lors de l’exécution de la commande. Toutefois, toutes les valeurs de propriété par défaut sont affichées à l’écran.

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a>Vérifier les serveurs Edge et leurs paramètres

Les informations de serveur Edge peuvent être récupérées à l’aide de Windows PowerShell. Cette commande retourne des informations sur tous les serveurs Edge configurés pour être utilisés dans votre organisation :

`Get-CsService -EdgeServer`

Les informations renvoyées incluent tous les paramètres de nom de domaine complet et de port pour chaque serveur Edge :

Identity : EdgeServer : dc.fabrikam.com

Serveur d’inscriptions : serveur d’inscriptions : LYNC-SE.fabrikam.com

AccessEdgeInternalSipPort : 5061

AccessEdgeExternalSipPort : 5061

AccessEdgeClientPort : 443

DataPsomServerPort : 8057

DataPsomClientPort : 444

MediaRelayAuthEdgePort : 5062

MediaRelayAuthInternalTurnTcpPort : 443

MediaRelayAuthExternalTurnTcpPort : 445

MediaRelayAuthInternalTurnUdpPort : 3478

MediaRelayAuthExternalTurnUdpPort : 3478

MediaCommunicationPortStart : 50000

MediaComunicationPortCount : 10000

AccessEdgeExternalFqdn : dc.fabrikam.com

DataEdgeExternalFqdn : dc.fabrikam.com

AVEdgeExternalFqdn :

InternalInterfaceFqdn :

ExternalMrasFqdn : dc.fabrikam.com

DependentServiceList : {Registrar : LYNC-SE.fabrikam.com,

Conferenceserver : LYNC-SE. fabrikam

com, MediationServer : LYNC-SE.

fabrikam.com}

ServiceId : fabrikam.com-EdgeServer-2

SiteId : site :fabrikam. com

PoolFqdn : dc.fabrikam.com

Version : 5

Rôle : EdgeServer

<div>

## <a name="check-federation-settings"></a>Vérifier les paramètres de Fédération

Vérifier les paramètres de Fédération, par exemple, si elle est configurée et, si la réponse est « oui », le nom de domaine complet et le port. La Fédération est activée et désactivée à l’aide de la collection globale des paramètres de configuration du serveur Edge d’accès. Cela signifie, entre autres, que la Fédération est configurée sur une base tout ou rien : soit la Fédération est activée pour l’ensemble de l’organisation, soit la Fédération est désactivée pour l’ensemble de l’Organisation

Vos paramètres de configuration du serveur Edge d’accès peuvent être renvoyés à l’aide de Windows PowerShell. Pour ce faire, exécutez la commande Windows PowerShell suivante :

`Get-CsAccessEdgeConfiguration`

À son tour, cette commande renvoie des données semblables à ceci :

Identity : global

AllowAnonymousUsers : false

AllowFederatedUsers : false

AllowOutsideUsers : false

To ClearingHouse : false

EnablePartnerDiscovery : false

EnableArchivingDisclaimer : false

KeepCrlsUpToDateForPeers : true

MarkSourceVerifiableOnOutgoingMessages : true

OutgoingTlsCountForFederatedPartners : 4

RoutingMethod : UseDnsSrvRouting

Si la propriété **AllowFederatedUsers** est définie sur true, cela signifie que la Fédération est activée pour votre organisation. (Définir **AllowFederatedUsers** sur true signifie également que, dans un scénario de domaine fractionné, vos utilisateurs locaux pourront communiquer de façon transparente avec vos utilisateurs dans le Cloud.)

Pour récupérer le nom de domaine complet et les paramètres de port de votre serveur Edge, reportez-vous à la tâche précédente (serveurs Edge et leurs paramètres).

L’activation de la Fédération au niveau de l’étendue globale signifie que les utilisateurs peuvent éventuellement communiquer avec des utilisateurs fédérés. Pour déterminer si des utilisateurs individuels peuvent communiquer avec des utilisateurs fédérés, vous devez examiner la stratégie d’accès des utilisateurs externes attribuée à cet utilisateur.

Les informations d’accès des utilisateurs externes peuvent être renvoyées à l’aide de Windows PowerShell. Par exemple, cette commande renvoie des informations sur la stratégie d’accès des utilisateurs externes globale :

`Get-CsExternalAccessPolicy -Identity "Global"`

Cette commande renvoie les informations de toutes les stratégies d’accès des utilisateurs externes :

`Get-CsExternalAccessPolicy`

Les informations renvoyées ressembleront à ceci :

Identity : false

Description

EnableFederationAccess : false

EnablePublicCloudAccess : false

EnablePublicCloudAccessAudioVideoAccess : false

EnableOutsideAccess : false

Si **EnableFederationAccess** est défini sur true, les utilisateurs gérés par la stratégie donnée peuvent communiquer avec des utilisateurs fédérés.

</div>

</div>

<div>

## <a name="check-archiving-settings"></a>Vérifier les paramètres d’archivage

Vérifier les paramètres d’archivage pour les communications internes et fédérées. Avant de vérifier les paramètres pour l’archivage interne et externe, vous devez vérifier que l’archivage est activé.

Les paramètres de configuration de l’archivage peuvent être vérifiés à l’aide de Windows PowerShell et de l’applet de commande Get-CsArchivingConfiguration :

`Get-CsArchivingConfiguration -Identity "Global"`

Notez que les paramètres d’archivage peuvent également être configurés au niveau de l’étendue site. Pour renvoyer des informations sur tous les paramètres d’archivage, utilisez la commande suivante :

`Get-CsArchivingConfiguration`

L’applet de commande Get-CsArchivingConfiguration renvoie des données semblables à ceci :

Identity : global

EnableArchiving : false

EnablePurging : false

PurgeExportedArchivesOnly : false

BlockOnArchiveFailure : false

KeepArchivingDataForDays : 14

PurgeHourOfDay : 2

Archiveduplicatemessages a : true

CachePurgingInterval : 24

Si la propriété EnableArchiving est définie sur false, cela signifie qu’aucune session de communication ne sera archivée. Si vous souhaitez archiver les sessions de messagerie instantanée uniquement, utilisez une commande comme celle qui suit pour activer l’archivage des sessions de messagerie instantanée :

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

Pour archiver les sessions de conférence et les sessions de messagerie instantanée, utilisez la commande suivante :

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

Si vous souhaitez comparer vos paramètres d’archivage actuels et les paramètres par défaut, exécutez la commande Windows PowerShell suivante :

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

Cette commande crée une instance en mémoire uniquement des paramètres de configuration d’archivage globaux. Il ne s’agit pas d’une collection réelle de paramètres utilisés par Lync Server. Toutefois, il affiche les valeurs par défaut pour toutes les propriétés de configuration de l’archivage.

Vous pouvez également utiliser cette commande pour renvoyer le nom de domaine complet de vos serveurs d’archivage :

`Get-CsService -ArchivingServer`

Une fois que vous avez vérifié que l’archivage est activé, vous pouvez afficher vos stratégies d’archivage pour déterminer si les sessions de communication interne et externe sont en cours d’archivage.

Les informations de stratégie d’archivage peuvent être récupérées à l’aide de la cmdlet Get-CsArchivingPolicy. Par exemple, cette commande renvoie des informations sur la stratégie d’archivage globale :

`Get-CsArchivingPolicy -Identity "Global"`

Étant donné que les stratégies d’archivage peuvent également être configurées au niveau du site et de l’étendue par utilisateur, vous pouvez également utiliser cette commande, qui retourne des informations sur toutes les stratégies d’archivage :

`Get-CsArchivingPolicy`

Les informations que vous recevez d' Get-CsArchivingPolicy ressemblent à ceci :

Identity : global

Description

ArchiveInternal : false

ArchiveExternal : false

Notez que, par défaut, l’archivage interne et externe est désactivé dans une stratégie d’archivage.

</div>

<div>

## <a name="check-cdr-settings"></a>Vérifier les paramètres CDR

Vérifiez les paramètres d’enregistrement des détails des appels (CDR) pour l’enregistrement des détails des appels d’égal à égal, de conférence et de conférence. Des informations détaillées sur vos paramètres CDR peuvent être renvoyées à l’aide de la cmdlet **Get-applet cscdrconfiguration** . Par exemple, cette commande renvoie des informations sur la collection globale de paramètres de configuration CDR :

`Get-CsCdrConfiguration -Identity "Global"`

Étant donné que les enregistrements des détails des appels peuvent également être configurés au niveau de l’étendue site, vous pouvez également exécuter cette commande, qui retourne des informations sur tous les paramètres de configuration CDR :

`Get-CsCdrConfiguration`

L’applet de commande Get-CsCdrConfiguration renvoie des informations similaires à celles-ci pour chaque collection de paramètres de configuration CDR :

Identity : global

EnableCDR : true

EnablePurging : true

KeepCallDetailForDays : 60

KeepErrorReportForDays : 60

PurgeHourOfDay : 2

Des informations similaires peuvent être renvoyées pour la surveillance QoE à l’aide de la cmdlet Get-CsQoEConfiguration. Par exemple, cette commande renvoie des informations sur la collection globale des paramètres de configuration QoE :

`Get-QoEConfiguration -Identity "Global"`

Ces informations ressembleront à ceci :

Identity : global

ExternalConsumerIssuedCertId :

EnablePurging : true

KeepQoEDataForDays : 60

PurgeHourOfDay : 1

EnableExternalConsumer : false

ExternalConsumerName :

ExternalConsumerURL :

EnableQoE : true

Si vous souhaitez comparer vos paramètres de CD-r actuels avec les paramètres CDR par défaut, vous pouvez examiner les valeurs par défaut en exécutant la commande suivante :

`New-CsCdrConfiguration -Identity "Global" -InMemory`

De même, les valeurs par défaut de la surveillance QoE peuvent être récupérées à l’aide de la commande suivante :

`New-CsQoEConfiguration -Identity "Global" -InMemory`

Vous pouvez également renvoyer le nom de domaine complet de vos serveurs de surveillance en exécutant la commande suivante :

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a>Vérifier les paramètres vocaux

Les paramètres vocaux généralement importants pour les administrateurs sont contenus dans des stratégies de voix et des itinéraires de communications vocales : les stratégies de voix contiennent les paramètres qui déterminent les fonctionnalités exposées aux utilisateurs individuels (comme la possibilité de transférer ou de transférer des appels), tandis que les itinéraires vocaux déterminent la façon dont les appels (et si) sont acheminés via le réseau téléphonique commuté.

Les informations de stratégie de voix peuvent être récupérées à l’aide de Windows PowerShell. Par exemple, cette commande renvoie des informations sur la stratégie de voix globale :

`Get-CsVoicePolicy -Identity "Global"`

Cette commande renvoie des informations sur toutes les stratégies de voix configurées pour être utilisées dans l’Organisation :

`Get-CsVoicePolicy`

Les informations renvoyées par la cmdlet Get-CsVoicePolicy ressemblent à ce qui suit :

Identity : global

PstnUsages {}

Description

AllowSimulRing : true

AllowCallForwarding : true

AllowPSTNReRouting : true

Nom : DefaultPolicy

EnableDelegation : true

EnableTeamCall : true

EnableCallTransfer : true

EnableCallPark : false

EnableMaliciousCallTracing : false

EnableBWPolicyOverride : false

PreventPSTNTollBypass : false

Vous pouvez également créer des requêtes qui retournaient un sous-ensemble de vos stratégies de voix. Par exemple, cette commande renvoie toutes les stratégies de voix qui autorisent le transfert d’appel :

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

Cette commande renvoie toutes les stratégies de voix qui n’autorisent pas le transfert d’appel :

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

Dans Windows PowerShell, utilisez l’applet de commande Get-CsVoiceRouting pour renvoyer des informations sur vos itinéraires vocaux :

`Get-CsVoiceRoute`

Cette commande renvoie des informations comme celles-ci pour tous les itinéraires des communications vocales :

Identity : LocalRoute

Priorité : 0

Description

NumberPattern : ^ ( \\ + 1 \[ 0-9 \] {10} ) $

PstnUsages {}

PstnGatewayList : {}

Nom : LocalRoute

SuppressCallerId :

AlternateCallerId :

Lync Server vous permet de créer des itinéraires vocaux qui n’ont pas d’utilisation PSTN et qui ne spécifient pas de passerelle PSTN. Toutefois, vous ne pouvez pas acheminer les appels via un itinéraire des communications vocales pour lequel ces deux valeurs de propriétés ne sont pas configurées. Pour cette raison, il peut s’avérer utile d’exécuter régulièrement cette commande, qui renvoie l’identité de n’importe quel itinéraire des communications vocales qui n’a pas d’utilisation PSTN :

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

De même, cette commande renvoie l’identité de tout itinéraire des communications vocales qui n’a pas été configuré pour disposer d’une passerelle PSTN :

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a>Vérifier les paramètres du service de conférence

Vérifier les paramètres du service de conférence pour la Conférence rendez-vous PSTN. Les paramètres du service de surveillance de conférence ne peuvent être récupérés qu’à l’aide de la cmdlet **Get-CsDialInConferencingConfiguration** . Ces paramètres ne sont pas disponibles dans le panneau de configuration Lync Server. Pour afficher vos paramètres de surveillance des conférences, utilisez une commande Windows PowerShell semblable à la suivante, qui renvoie la collection globale des paramètres du service d’assistance de conférence :

`Get-CsDialInConferencingConfiguration -Identity "Global"`

Notez que les paramètres du service de surveillance de conférence peuvent également être configurés au niveau de l’étendue site. Pour renvoyer des informations sur tous les paramètres du service de conférence, utilisez plutôt cette commande :

`Get-CsDialInConferencingConfiguration`

L’applet de commande Get-CsDialInConferencingConfiguration renvoie des données semblables à ceci :

Identity : global

EntryExitAnnouncementsType : UseNames

EnableNameRecording : true

EntryExitAnnouncementsEnabledByDefault : false

Si EntryExitAnnouncementsEnabledByDefault est défini sur false, cela signifie que les annonces de conférence sont désactivées. Pour activer les annonces d’entrée et de sortie, exécutez une commande Windows PowerShell semblable à celle-ci :

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Get-CsSipDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-CsAccessEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Get-applet csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[Get-applet cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[Get-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[Get-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

