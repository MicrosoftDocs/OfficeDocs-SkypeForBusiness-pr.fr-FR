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
ms.openlocfilehash: ec1dea4ad3d5052bc2ba23cccd9e19ab138414ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a>Afficher l’état des paramètres globaux pour une forêt dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-20_

Les administrateurs doivent vérifier les paramètres globaux d’un déploiement de Lync Server 2013 au mois. L’objectif consiste à passer en revue des paramètres implémentés à l’aide d’un ensemble de configurations connues : une configuration de référence pour garantir que les paramètres soient valides et déterminez si la documentation de référence doit être mise à jour. Les modifications apportées au paramètre global doivent être implémentées par le biais d’un processus de contrôle des modifications qui devrait inclure la documentation des nouveaux paramètres.

Les paramètres globaux qui doivent être examinés sont décrits dans les sections suivantes :

<div>

## <a name="check-general-settings"></a>Vérifier les paramètres généraux

Vérifiez les paramètres généraux, y compris les domaines compatibles SIP (Session Initiation Protocol) pour Lync Server 2013.

Les informations de domaine SIP peuvent être renvoyées à l’aide de Windows PowerShell et de l’applet **de cmdlet Get-CsSipDomain** . Pour obtenir ces informations, exécutez la `Get-CsSipDomain` commande Windows PowerShell.

Get-CsSipDomain renverra des informations similaires à ce qui suit pour tous les domaines SIP autorisés :

Nom d’identité IsDefault

\-------- ---- ---------

fabrikam.com fabrikam.com true

na.fabrikam.com na.fabrikam.com false

Si la propriété IsDefault est définie sur true, le domaine correspondant est le domaine SIP par défaut. Vous pouvez utiliser l’applet de cmdlet Set-CsSipDomain pour modifier le domaine SIP par défaut de votre organisation. Toutefois, vous ne pouvez pas supprimer le domaine SIP par défaut, car cela vous laisserait sans domaine par défaut. Si vous souhaitez supprimer le domaine fabrikam.com (comme illustré dans l’exemple précédent), vous devez commencer par configurer na.fabrikam.com comme domaine par défaut.

</div>

<div>

## <a name="check-meeting-settings"></a>Vérifier les paramètres de la réunion

Les paramètres de réunion incluent les définitions de stratégie de réunion et la prise en charge de la participation d’utilisateurs anonymes à des réunions.

Les paramètres de configuration de réunion peuvent être récupérés à l’aide de Windows PowerShell et de l’applet **de cmdlet Get-CsMeetingConfiguration** . Par exemple, la commande suivante renvoie des informations sur les paramètres de configuration de la réunion globale :

Get-CsMeetingConfiguration-Identity les paramètres de configuration de la réunion « global » peuvent également être configurés sur l’étendue du site. Pour cette raison, vous souhaiterez peut-être utiliser la commande suivante qui renvoie des informations sur tous les paramètres de configuration de la réunion :

`Get-CsMeetingConfiguration`

L’applet de commande **Get-CsMeetingConfiguration** renvoie des informations similaires à ce qui suit :

Identity : global

PstnCallersBypassLobby : true

EnableAssignedConferenceType : true

DesignateAsPresenter : société

AssignedConferenceTypeByDefault : true

AdmitAnonymousUsersByDefault : true

Là encore, le dernier élément de la liste, **AdmitAnonymousUsersByDefault**, active ou désactive la possibilité pour les utilisateurs anonymes de participer aux réunions.

Lors de la vérification des paramètres de configuration de la réunion, vous trouverez peut-être utile de comparer les paramètres actuels par rapport aux équivalents par défaut. Vous pouvez afficher les paramètres de configuration de la réunion par défaut en exécutant la commande suivante :

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

La commande précédente crée une instance en mémoire uniquement des paramètres de configuration de réunion globale, une instance qui utilise la valeur par défaut pour chaque propriété. Aucun paramètre de configuration de réunion réel n’est créé lors de l’exécution de la commande. Toutefois, toutes les valeurs de propriété par défaut s’affichent à l’écran.

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a>Vérifier les serveurs Edge et leurs paramètres

Vous pouvez récupérer les informations sur le serveur Edge à l’aide de Windows PowerShell. Cette commande renvoie des informations sur tous les serveurs Edge configurés pour une utilisation au sein de votre organisation :

`Get-CsService -EdgeServer`

Les informations renvoyées incluent tous les paramètres de nom de domaine complet et de port de chaque serveur Edge :

Identité : EdgeServer : dc.fabrikam.com

Bureau d’enregistrement : LYNC-SE.fabrikam.com

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

ConferencingServer : LYNC-SE. fabrikam

com, MediationServer : LYNC-SE.

fabrikam.com}

ServiceId : fabrikam.com-EdgeServer-2

SiteId : site :fabrikam. com

PoolFqdn : dc.fabrikam.com

Version : 5

Rôle : EdgeServer

<div>

## <a name="check-federation-settings"></a>Vérifier les paramètres de Fédération

Vérifiez les paramètres de Fédération (par exemple, s’il est configuré et, si la réponse est « oui »), les nom de domaine complet et port. La Fédération est activée et désactivée à l’aide de l’ensemble global de paramètres de configuration de Microsoft Edge. Entre autres choses, cela signifie que la Fédération est configurée sur une base « tout-le » : une Fédération est activée pour l’ensemble de l’organisation ou la Fédération est désactivée pour l’ensemble de l’organisation.

Les paramètres de configuration de Microsoft Edge peuvent être retournés à l’aide de Windows PowerShell. Pour cela, exécutez la commande Windows PowerShell suivante :

`Get-CsAccessEdgeConfiguration`

Ensuite, cette commande renvoie des données similaires à ce qui suit :

Identity : global

AllowAnonymousUsers : false

AllowFederatedUsers : false

AllowOutsideUsers : false

Concentrez-vous : faux

EnablePartnerDiscovery : false

EnableArchivingDisclaimer : false

KeepCrlsUpToDateForPeers : true

MarkSourceVerifiableOnOutgoingMessages : true

OutgoingTlsCountForFederatedPartners : 4

RoutingMethod : UseDnsSrvRouting

Si la propriété **AllowFederatedUsers** est définie sur true, cela signifie que la Fédération est activée pour votre organisation. (Si vous définissez la propriété **AllowFederatedUsers** sur true, dans un scénario de domaine fractionné, vos utilisateurs locaux pourront communiquer en toute transparence avec vos utilisateurs dans le Cloud.)

Pour récupérer les paramètres de nom de domaine complet et de port de votre serveur Edge, voir la tâche précédente (serveurs de bord et leurs paramètres).

L’activation de la Fédération au niveau de l’étendue globale signifie que les utilisateurs peuvent éventuellement communiquer avec des utilisateurs fédérés. Pour déterminer si des utilisateurs individuels peuvent communiquer avec des utilisateurs fédérés, vous devez examiner la stratégie d’accès des utilisateurs externes affectée à cet utilisateur.

Les informations d’accès des utilisateurs externes peuvent être renvoyées à l’aide de Windows PowerShell. Par exemple, cette commande renvoie des informations sur la stratégie globale d’accès des utilisateurs externes :

`Get-CsExternalAccessPolicy -Identity "Global"`

Cette commande renvoie des informations pour toutes les stratégies d’accès des utilisateurs externes :

`Get-CsExternalAccessPolicy`

Les informations renvoyées sont similaires à ce qui suit :

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

Vérifiez les paramètres d’archivage des communications internes et fédérées. Avant de vérifier les paramètres de l’archivage interne et externe, vérifiez que l’archivage est activé.

Les paramètres de configuration de l’archivage peuvent être vérifiés à l’aide de Windows PowerShell et de l’applet de passe Get-CsArchivingConfiguration :

`Get-CsArchivingConfiguration -Identity "Global"`

Notez que vous pouvez également configurer les paramètres d’archivage à l’étendue du site. Pour renvoyer des informations sur les paramètres d’archivage, utilisez la commande suivante :

`Get-CsArchivingConfiguration`

L’applet de requête get-CsArchivingConfiguration renvoie des données similaires à ce qui suit :

Identity : global

EnableArchiving : false

EnablePurging : false

PurgeExportedArchivesOnly : false

BlockOnArchiveFailure : false

KeepArchivingDataForDays : 14

PurgeHourOfDay : 2

ArchiveDuplicateMessages : true

CachePurgingInterval : 24

Si la propriété EnableArchiving est définie sur false, cela signifie qu’aucune session de communication n’est archivée. Si vous voulez uniquement archiver des sessions de messagerie instantanée, utilisez une commande telle que celle qui suit pour activer l’archivage des sessions de messagerie instantanée :

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

Pour archiver des sessions de conférence et des sessions de messagerie instantanée, utilisez la commande suivante :

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

Si vous souhaitez comparer vos paramètres d’archivage actuels avec les paramètres par défaut, exécutez la commande Windows PowerShell suivante :

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

Cette commande crée une instance en mémoire uniquement des paramètres de configuration de l’archivage global. Ce n’est pas une collection réelle de paramètres qui est utilisée par Lync Server. Toutefois, elle affiche les valeurs par défaut de toutes les propriétés de configuration de l’archivage.

Vous pouvez également utiliser cette commande pour renvoyer le nom de domaine complet de vos serveurs d’archivage :

`Get-CsService -ArchivingServer`

Après vérification de l’activation de l’archivage, vous pouvez afficher vos politiques d’archivage pour déterminer si les sessions internes et externes de communication sont archivées.

Vous pouvez récupérer les informations de stratégie d’archivage à l’aide de l’applet de passe Get-CsArchivingPolicy. Par exemple, cette commande renvoie des informations sur la stratégie d’archivage globale :

`Get-CsArchivingPolicy -Identity "Global"`

Étant donné que les stratégies d’archivage peuvent également être configurées au niveau du site et de l’étendue par utilisateur, vous pouvez également utiliser cette commande pour renvoyer des informations sur toutes les stratégies d’archivage :

`Get-CsArchivingPolicy`

Les informations que vous recevez de Get-CsArchivingPolicy sont les suivantes :

Identity : global

Description

ArchiveInternal : false

ArchiveExternal : false

Notez que, par défaut, l’archivage interne et externe est désactivé dans une stratégie d’archivage.

</div>

<div>

## <a name="check-cdr-settings"></a>Vérifier les paramètres CDR

Vérifiez les paramètres d’enregistrement des détails des appels (CDR) pour l’enregistrement des détails des appels d’égal à égal, de conférence et d’appel vocal. Des informations détaillées sur vos paramètres CDR peuvent être renvoyées à l’aide de l’applet **de passe Get-CsCdrConfiguration** . Par exemple, cette commande renvoie des informations sur la collection globale de paramètres de configuration de CDR :

`Get-CsCdrConfiguration -Identity "Global"`

Comme CDR peut également être configuré sur l’étendue du site, vous souhaiterez peut-être également exécuter cette commande, qui renvoie des informations sur tous les paramètres de configuration de CDR :

`Get-CsCdrConfiguration`

L’applet de requête get-CsCdrConfiguration renvoie des informations similaires à ce qui suit pour chaque collection de paramètres de configuration CDR :

Identity : global

EnableCDR : true

EnablePurging : true

KeepCallDetailForDays : 60

KeepErrorReportForDays : 60

PurgeHourOfDay : 2

Des informations similaires peuvent être renvoyées pour la surveillance QoE en utilisant l’applet de requête get-CsQoEConfiguration. Par exemple, cette commande renvoie des informations sur la collection globale de paramètres de configuration QoE :

`Get-QoEConfiguration -Identity "Global"`

Cette information ressemble à ceci :

Identity : global

ExternalConsumerIssuedCertId :

EnablePurging : true

KeepQoEDataForDays : 60

PurgeHourOfDay : 1

EnableExternalConsumer : false

ExternalConsumerName :

ExternalConsumerURL :

EnableQoE : true

Si vous souhaitez comparer vos paramètres de CDR actuels avec les paramètres CDR par défaut, les valeurs par défaut peuvent être examinées en exécutant la commande suivante :

`New-CsCdrConfiguration -Identity "Global" -InMemory`

De même, les valeurs par défaut pour la surveillance QoE peuvent être récupérées à l’aide de la commande suivante :

`New-CsQoEConfiguration -Identity "Global" -InMemory`

Vous pouvez également renvoyer le nom de domaine complet de vos serveurs de surveillance en exécutant la commande suivante :

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a>Vérifier les paramètres de la voix

Les paramètres vocaux sont généralement importants pour les administrateurs dans les politiques vocales et les itinéraires vocaux : les stratégies vocales contiennent les paramètres qui déterminent les fonctionnalités exposées aux utilisateurs individuels (par exemple, la possibilité de transférer ou de transférer les appels), tout en les itinéraires vocaux déterminent la manière dont les appels (et si) sont routés sur le RTC.

Les informations de la stratégie vocale peuvent être récupérées à l’aide de Windows PowerShell. Par exemple, la commande suivante renvoie des informations sur la politique vocale globale :

`Get-CsVoicePolicy -Identity "Global"`

Cette commande renvoie des informations sur toutes les stratégies vocales configurées pour une utilisation au sein de l’Organisation :

`Get-CsVoicePolicy`

Les informations renvoyées par la cmdlet Get-CsVoicePolicy sont similaires à ce qui suit :

Identity : global

PstnUsages :{}

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

Vous pouvez également créer des requêtes qui renvoient un sous-ensemble de vos stratégies vocales. Par exemple, cette commande renvoie toutes les stratégies vocales qui autorisent le transfert d’appel :

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

Ainsi, cette commande renvoie toutes les stratégies vocales qui n’autorisent pas le transfert d’appel :

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

Dans Windows PowerShell, vous pouvez utiliser l’applet de passe Get-CsVoiceRouting pour renvoyer des informations sur vos itinéraires vocaux :

`Get-CsVoiceRoute`

Cette commande renvoie des informations telles que celle-ci pour tous les itinéraires vocaux :

Identité : LocalRoute

Priorité : 0

Description

NumberPattern : ^ (\\+ 1\[0-9\]{10}) $

PstnUsages :{}

PstnGatewayList :{}

Nom : LocalRoute

SuppressCallerId :

AlternateCallerId :

Lync Server vous permet de créer des itinéraires vocaux sans utilisation PSTN et de ne spécifier aucune passerelle PSTN. Toutefois, vous ne pouvez pas acheminer les appels sur un itinéraire vocal qui ne possède pas les deux valeurs de propriété configurées. Pour cette raison, il peut être utile d’exécuter cette commande de manière périodique, qui renvoie l’identité d’un itinéraire vocal sans utilisation RTC :

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

De même, cette commande renvoie l’identité d’un itinéraire vocal qui n’a pas été configuré pour avoir une passerelle RTC :

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a>Vérifier les paramètres du surveillant de conférences

Vérifiez les paramètres du surveillant de conférences pour la Conférence rendez-vous PSTN. Les paramètres du surveillant de conférences peuvent uniquement être récupérés à l’aide de l’applet de passe **Get-CsDialInConferencingConfiguration** . Ces paramètres ne sont pas disponibles dans le panneau de configuration de Lync Server. Pour afficher les paramètres de votre surveillant de conférences, utilisez une commande Windows PowerShell semblable à la suivante qui renvoie la collection globale de paramètres du surveillant de conférences :

`Get-CsDialInConferencingConfiguration -Identity "Global"`

Notez que les paramètres du surveillant de conférences peuvent également être configurés sur l’étendue du site. Pour renvoyer des informations sur tous les paramètres du surveillant de conférences, utilisez la commande suivante :

`Get-CsDialInConferencingConfiguration`

L’applet de requête get-CsDialInConferencingConfiguration renvoie des données similaires à ce qui suit :

Identity : global

EntryExitAnnouncementsType : UseNames

EnableNameRecording : true

EntryExitAnnouncementsEnabledByDefault : false

Si EntryExitAnnouncementsEnabledByDefault est défini sur false, cela signifie que les annonces de conférences sont désactivées. Pour activer les annonces d’entrée et de sortie, exécutez une commande Windows PowerShell semblable à ce qui suit :

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Get-CsSipDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-CsAccessEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Get-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
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

