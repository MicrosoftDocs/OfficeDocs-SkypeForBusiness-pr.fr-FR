---
title: 'Lync Server 2013 : Configuration requise pour la résistance des sites de succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ff969638f8c46abdd0ebcc8d11821a6a31b3c76
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a>Configuration requise pour la résistance des sites de succursale pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-02-25_

Cette rubrique a pour but de vous aider à préparer les utilisateurs à la résistance des sites de succursale et à la survivabilité de la messagerie vocale, et indique également les configurations matérielles et logicielles correspondantes requises.

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a>Préparation des utilisateurs de succursale à la résistance des sites de succursale

Préparez les utilisateurs à la résilience de site de succursale en définissant leur pool de bureaux d’enregistrement comme étant le serveur de succursales Survivables (SBA) ou le serveur de succursale survivant.

<div>

## <a name="registrar-assignments-for-branch-users"></a>Affectations de serveurs d’inscriptions aux utilisateurs de succursale

Quelle que soit la solution de résistance de site de succursale choisie, vous devez affecter un serveur d’inscriptions principal à chaque utilisateur. Les utilisateurs du site de succursale doivent toujours s’inscrire auprès du Bureau d’enregistrement au niveau de la succursale, qu’il s’agisse de bureaux d’enregistrement, de succursales survivables ou d’un serveur Lync Server 2013 standard ou Enterprise Edition Server. Un enregistrement de ressource de service (SRV) DNS (Domain Name System) est requis pour qu’un client puisse détecter automatiquement son pool de serveurs d’inscriptions. Si l’unité de branchement Survivable devient indisponible, c’est la façon dont les clients du site de succursale découvrent automatiquement le Bureau d’enregistrement de sauvegarde.

Si un site de succursale ne possède pas de serveur DNS, il existe deux façons de configurer la découverte de l’appareil de succursales survivant ou du serveur de succursales survivant:

  - Configurez l’option DHCP 120 sur le serveur DHCP (Dynamic Host Configuration Protocol) du site de succursale de manière à ce qu’elle pointe vers le nom de domaine complet (FQDN) de l’appareil ou du serveur de succursales survivant.

  - Configurez l’application branche Survivable ou le serveur de succursales survivant pour répondre aux requêtes 120 DHCP.

</div>

<div>

## <a name="voice-routing-for-branch-users"></a>Routage des communications vocales des utilisateurs de succursale

Nous vous recommandons de créer une stratégie VoIP (Voice over Internet Protocol) distincte au niveau utilisateur pour les utilisateurs d’un site de succursale. Il doit s’agir d’un itinéraire principal qui utilise l’appareil de branchement ou la passerelle serveur survivant, et un ou plusieurs itinéraires de sauvegarde qui utilisent une passerelle de réseau téléphonique commuté (PSTN) sur le site central. Si l’itinéraire principal n’est pas disponible, l’itinéraire alternatif faisant appel à une ou plusieurs passerelles de site central est utilisé à la place. Ainsi, quel que soit l’endroit où l’utilisateur est inscrit, soit sur le serveur d’inscriptions du site de succursale, soit sur le pool de serveurs d’inscriptions de sauvegarde du site central, la stratégie VoIP de l’utilisateur est toujours appliquée. Il est primordial de tenir compte de ce point pour les scénarios de basculement. Par exemple, si vous avez besoin de renommer l’unité de branchement Survivable ou de reconfigurer l’unité de branchement Survivable pour vous connecter à un pool d’bureaux de connexion sur le site central, vous devez déplacer les utilisateurs du site de succursale vers le site central pour la durée. (Pour plus d’informations sur le changement de nom d’une unité de branchement Survivable, voir [annexe B: gestion d’une unité de succursale Survivable dans Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) dans la documentation de déploiement.) Si ces utilisateurs ne disposent pas de stratégies VoIP au niveau utilisateur ou d’un plan de numérotation de niveau utilisateur, lorsque les utilisateurs sont déplacés vers un autre site, les stratégies VoIP de niveau de site et les plans de numérotation de niveau site du site central s’appliquent par défaut aux utilisateurs, et non au niveau VoIP du site de la succursale. politiques et plans de numérotation. Dans ce scénario, leurs appels échoueront, à moins que les stratégies VoIP et les plans de numérotation au niveau du site utilisés par le pool de serveurs d’inscriptions de sauvegarde puissent également s’appliquer aux utilisateurs du site de succursale. Par exemple, si les utilisateurs d’un site de succursale basé au Japon sont déplacés sur un site central situé à Redmond, il est probable qu’un plan de numérotation dont les règles de normalisation ajoutent le préfixe +1425 à tous les appels à 7 chiffres ne traduiront pas correctement les appels de ces utilisateurs.

<div>


> [!IMPORTANT]  
> Lorsque vous créez un itinéraire alternatif de succursale, nous vous conseillons d’ajouter deux enregistrements d’utilisation téléphonique RTC à la stratégie utilisateur de succursale et d’affecter des itinéraires distincts à chacun d’entre eux. Le premier itinéraire, ou principal, dirigerait les appels vers la passerelle associée à l’appareil de branchement (SBA) ou au serveur de succursales survivant. le deuxième, ou la sauvegarde, route dirigerait les appels vers la passerelle sur le site central. En dirigeant les appels, le SBA ou le serveur de succursale tente tous les itinéraires affectés au premier enregistrement d’utilisation RTC avant d’essayer le deuxième enregistrement.



</div>

Pour garantir que les appels entrants vers les utilisateurs du site de filiale seront indisponibles lorsque la passerelle de succursale ou le composant Windows du site de l’appareil de succursale survivant est indisponible (qui se produit, par exemple, si l’appareil ou la succursale est survivant la passerelle a été mise en place pour la maintenance), créez un itinéraire de basculement sur la passerelle (ou travaillez avec votre fournisseur de numérotation directe) pour rediriger les appels entrants vers le pool d’inscriptions de sauvegarde sur le site central. À partir de là, les appels sont routés sur la liaison de réseau étendu (WAN) en direction des utilisateurs de succursale. Assurez-vous que l’itinéraire convertit les numéros selon les formats de numéro de téléphone acceptés par la passerelle RTC ou un autre homologue de jonction. Pour plus d’informations sur la création d’un itinéraire de basculement, voir [configuration d’un itinéraire de basculement dans Lync Server 2013](lync-server-2013-configuring-a-failover-route.md). De même, créez des plans de numérotation au niveau du service pour la jonction associée à la passerelle du site de succursale afin de normaliser les appels entrants. Si vous avez deux appareils de succursales Survivables dans un site de succursale, vous pouvez créer un plan de numérotation de niveau site pour les deux, sauf si un plan de niveau de service distinct est nécessaire pour chacun d’eux.

<div>


> [!NOTE]  
> Pour calculer la consommation des ressources du site central par les utilisateurs de site de succursale qui recourent au site central pour accéder aux fonctionnalités de présence, de conférence ou de basculement, nous vous conseillons de considérer chaque utilisateur de site de succursale comme s’il était inscrit sur le site central. Il n’existe actuellement aucune limite sur le nombre d’utilisateurs de sites de succursales, y compris les utilisateurs enregistrés auprès d’une unité de succursale Survivable.



</div>

Nous vous recommandons également de créer un plan de numérotation et une stratégie de voix au niveau utilisateur, et de les affecter aux utilisateurs de site de succursale. Pour plus d’informations, reportez-vous à la rubrique [création d’un plan de numérotation dans Lync server 2013](lync-server-2013-create-a-dial-plan.md) et [création de la stratégie de routage VoIP pour les utilisateurs de succursales dans Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) dans la documentation de déploiement.

<div>

## <a name="routing-extension-numbers"></a>Acheminement des numéros de poste

Lorsque vous préparez des plans de numérotation et des stratégies vocales pour les utilisateurs de sites de succursales, veillez à inclure les règles de normalisation et les règles de traduction qui correspondent aux chaînes et au format de nombre utilisés dans l’attribut msRTCSIP-Line (ou URI de ligne), de sorte que les appels 2013 Lync soient activés entre les branches. les utilisateurs du site et les utilisateurs du site central seront routés correctement, en particulier lorsque les appels doivent être redirigés sur le RTC, car la liaison WAN n’est pas disponible. D’autres éléments sont à prendre en considération dans le cas des numéros composés incluant des numéros de poste, et pas seulement des numéros de téléphone.

Les règles de normalisation et de conversion qui correspondent à des URI de ligne contenant un numéro de poste, seul ou en plus d’un numéro de téléphone E.164 complet, imposent des exigences supplémentaires. Cette section décrit plusieurs exemples de scénarios pour acheminer les appels pour des URI de ligne constitués d’un numéro de poste.

Si votre organisation n’a pas de numéros de téléphone SDA (Sélection directe à l’arrivée) configurés pour les utilisateurs et que l’URI de ligne de chaque utilisateur est configuré avec *uniquement* un numéro de poste, les utilisateurs internes peuvent s’appeler en composant uniquement le numéro de poste. Cependant, vous devez configurer des règles de normalisation qui puissent s’appliquer aux appels d’un utilisateur d’un site de succursale à destination d’un utilisateur du site central qui correspondent aux numéros de poste.

Dans un scénario où la liaison de réseau étendu entre un site de succursale et un site central est disponible, les appels des utilisateurs du site de succursale à destination des utilisateurs du site central ne nécessitent pas de règle de normalisation correspondante pour convertir le numéro, car l’appel n’est pas acheminé sur le réseau téléphonique commuté. Par exemple :


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom de la règle</th>
<th>Description</th>
<th>Type de numéro</th>
<th>Conversion</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtensions</p></td>
<td><p>Ne convertit pas les numéros à 5 chiffres</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>$1</p></td>
<td><p>10001 n’est pas converti</p></td>
</tr>
</tbody>
</table>


Vous devez également faire face aux scénarios de numéros de poste spécifiques où la liaison de réseau étendu entre un site de succursale et un site central n’est pas disponible et où un appel émanant d’un site de succursale doit être acheminé sur le réseau téléphonique commuté. En cas de panne de réseau étendu, si l’utilisateur d’un site de succursale appelle un utilisateur du site central en composant uniquement le numéro de poste de ce dernier, vous devez disposer d’une règle de conversion sortante qui ajoute le numéro de téléphone complet de l’utilisateur du site central. Si l’URI de ligne d’un utilisateur contient le numéro de téléphone complet de votre organisation et le numéro de poste unique de l’utilisateur au lieu d’un numéro de téléphone complet propre à l’utilisateur, vous devez disposer d’une règle de conversion sortante qui ajoute le numéro de téléphone complet de l’organisation. Par exemple :


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Description</th>
<th>Modèle de correspondance</th>
<th>Conversion</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Traduit les numéros à 5 chiffres en numéro de téléphone d’utilisateur avec numéro de poste</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>+14255550123;poste=$1</p></td>
<td><p>10001 devient +14255550123;ext=10001</p></td>
</tr>
<tr class="even">
<td><p>Traduit les numéros à 5 chiffres en numéro de téléphone de votre organisation complété du poste d’un utilisateur</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>+14255550100;poste=$1</p></td>
<td><p>10001 devient +14255550100;ext=10001</p></td>
</tr>
</tbody>
</table>


Dans ce scénario, si l’homologue de jonction qui traite le réacheminement vers le réseau téléphonique commuté ne prend pas en charge les numéros de poste, la règle de conversion sortante doit également supprimer le numéro de poste. Par exemple :


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Description</th>
<th>Modèle de correspondance</th>
<th>Conversion</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Supprime le poste des numéros de téléphone présentant un numéro de poste</p></td>
<td><p>^\+(\d *); EXT = (\d*) $</p></td>
<td><p>+$1</p></td>
<td><p>+14255550123;ext=10001 devient +14255550123</p></td>
</tr>
</tbody>
</table>


Qu’une liaison de réseau étendu soit disponible ou pas, si votre organisation n’a pas de numéros SDA configurés pour les utilisateurs individuels et que l’URI de ligne d’un utilisateur contient le numéro de téléphone de votre organisation et le numéro de poste unique de l’utilisateur, vous devez configurer l’URI de ligne du numéro de téléphone de votre organisation avec un numéro joignable pour l’homologue de jonction ou la passerelle RTC du site de succursale. Vous devez également configurer l’URI de ligne du numéro de téléphone de votre organisation de sorte qu’il contienne son propre poste unique pour les appels devant être acheminés vers ce numéro.

Pour plus d’informations sur les appels d’un utilisateur de site central à un utilisateur de site d’une succursale lorsque le lien réseau étendu entre les sites n’est pas disponible, voir «préparation de la survie de la messagerie vocale» plus loin dans cette rubrique. Pour plus d’informations sur les plans de numérotation et les règles de normalisation, notamment d’autres exemples de règles, voir [plans de numérotation et règles de normalisation dans Lync server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) dans la documentation de planification et [Configuration des plans de numérotation dans Lync Server 2013](lync-server-2013-configuring-dial-plans.md) lors du déploiement. accompagnant. Pour plus d’informations sur les règles de traduction sortantes, voir [règles de traduction dans Lync server 2013](lync-server-2013-translation-rules.md) dans la documentation de planification et [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a>Préparation de la survivabilité de la messagerie vocale

En règle générale, la messagerie unifiée Exchange est uniquement installée sur un site central et non sur des sites de succursales. Un appelant doit pouvoir laisser un message vocal, même si la liaison de réseau étendu entre un site de succursale et le site central n’est pas disponible. Par conséquent, la configuration de l’URI de ligne pour le numéro de téléphone du standard automatique de messagerie unifiée qui fournit des messages vocaux pour les utilisateurs du site de succursale nécessite des considérations spéciales, en plus de la stratégie vocale, du plan de numérotation et des règles de normalisation applicables à ce message vocal souche.

Les appareils de branchement survivables (SBAs) et les serveurs de succursales survivables permettent une survie de la messagerie vocale aux utilisateurs de succursales en cas de panne du réseau étendu. En particulier, si vous utilisez un appareil de succursale ou un serveur de succursales survivant et que le réseau WAN devient indisponible, le serveur de succursale SBA ou survivant redirige les appels sans réponse sur le RTC vers la messagerie unifiée Exchange sur le site central. Avec un serveur de succursale SBA ou Survivable, les utilisateurs peuvent également récupérer les messages vocaux par le biais du RTC lors d’une panne du réseau étendu. Enfin, au cours d’une période de connexion WAN, l’unité de succursale survivant ou le serveur de succursales survivant met en file d’attente des notifications d’appel en absence, puis les télécharge sur le serveur de messagerie unifiée Exchange lorsque le WAN est restauré. Pour vous assurer que le reroutage de messagerie vocale est résilient, veillez à ajouter une entrée pour le nom de domaine complet (FQDN) du pool de site central et une entrée pour le nom de domaine complet du serveur Edge au fichier hosts du serveur de succursales survivant. À défaut, il est possible que la résolution DNS arrive à expiration si vous ne disposez pas de serveur DNS sur le site de succursale.

Pour configurer la survivabilité de la messagerie vocale pour les utilisateurs de site de succursale, les configurations suivantes sont recommandées :

  - Un administrateur Microsoft Exchange doit configurer le standard automatique de messagerie unifiée (AA) Exchange pour accepter uniquement les messages. Cette configuration désactive toutes les autres fonctions génériques, comme le transfert à un utilisateur ou un opérateur, et limite le rôle du standard automatique à la seule réception des messages. Sinon, l’administrateur Exchange peut utiliser un standard automatique générique ou personnalisé pour router l’appel vers un opérateur.

  - L’administrateur du serveur Lync doit prendre le numéro de téléphone AA et utiliser ce numéro de téléphone en tant que numéro de **standard automatique de messagerie unifiée Exchange** dans les paramètres de routage de la messagerie vocale pour l’appareil ou le serveur de succursale survivant.

  - L’administrateur du serveur Lync doit obtenir le numéro de téléphone d’accès de l’abonné Exchange UM et utiliser ce numéro en tant que numéro d' **accès d’abonné** dans les paramètres de routage de la messagerie vocale de l’appareil ou du serveur de succursale Survivable.

  - L’administrateur du serveur Lync doit configurer la messagerie unifiée Exchange pour qu’un seul plan de numérotation soit associé à tous les utilisateurs de succursales qui ont besoin d’accéder à la messagerie vocale lors d’une panne du réseau étendu.

  - Lorsque la liaison de réseau étendu n’est pas disponible, les appels à destination des utilisateurs de site de succursale peuvent être acheminés vers la messagerie vocale de la messagerie unifiée Exchange de l’utilisateur, à condition toutefois que la stratégie de voix appliquée à l’appel spécifie un numéro de téléphone de messagerie vocale unique et qu’elle inclue un numéro de poste.

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Configuration matérielle et logicielle requise pour la résistance des sites de succursale

La configuration matérielle et logicielle requise varie en fonction de la solution de résistance.

<div>

## <a name="requirements-for-survivable-branch-appliances"></a>Configuration requise pour les Survivable Branch Appliances

Le matériel et le logiciel requis sont intégrés à l’appareil de branchement survivant. Cependant, il est également recommandé que chaque site de succursale déploie un serveur DHCP afin d’obtenir des adresses IP du client ; sinon, lorsque le bail DHCP expire, les clients ne disposent plus de connectivité IP.

Si les serveurs DNS d’entreprise sont situés uniquement dans des sites centraux, les utilisateurs du site de succursale ne seront pas en mesure de s’y connecter en cas de panne du réseau étendu, et par conséquent, la découverte de Lync Server qui utilise un enregistrement de ressource DNS SRV (service (SRV)) échouera. Pour garantir un réacheminement rapide lors d’une panne de réseau étendu, les enregistrements DNS doivent être mis en cache au niveau du site de succursale. Si le routeur de succursale prend en charge le cache DNS, activez-le à cette fin. Vous pouvez également déployer un serveur DNS au niveau de la succursale. Il peut s’agir d’un serveur autonome ou d’une version de l’application de succursale Survivable qui prend en charge les fonctionnalités DNS. Pour plus d’informations, contactez le fournisseur de votre appareil pour succursales survivant.

<div>


> [!NOTE]  
> Il n’est pas nécessaire de disposer d’un contrôleur de domaine sur un site de succursale. L’unité de branchement Survivable authentifie les clients en utilisant un certificat spécial qu’il envoie au client en réponse à la demande de certificat du client lors de la tentative de signature.



</div>

Les clients Lync peuvent découvrir le serveur Lync à l’aide de l’option DHCP option 120 (option d’inscription SIP). La configuration peut prendre l’une des deux formes suivantes :

  - Configurez le serveur DHCP sur le site de succursale pour répondre aux requêtes 120 DHCP, qui renvoient le nom de domaine complet du Bureau d’enregistrement sur l’appareil de succursales survivant ou le serveur de succursales survivant.

  - Activez le protocole DHCP de Lync Server. Lorsque celle-ci est activée, le Bureau d’enregistrement de serveurs Lync répond aux requêtes d’option DHCP 120. Notez que le serveur d’inscriptions ne répond pas aux requêtes DHCP autres que DHCP, option 120.

De plus, pour les sites de succursale plus importants disposant de plusieurs sous-réseaux, les agents de relais DHCP doivent être activés pour transférer les requêtes DHCP, option 120, au serveur DHCP (configuration 1) ou au serveur d’inscriptions (configuration 2).

Enfin, les utilisateurs du site de succursale doivent être configurés pour Enterprise Voice et approvisionnés avec un point de terminaison de communications unifié approprié.

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a>Configuration requise pour les serveurs Survivable Branch Server

La configuration requise pour les serveurs de succursales Survivables est la même que celle d’un serveur frontal. Pour plus d’informations, voir [plates-formes matérielles pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de planification.

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a>Conditions requises pour les déploiements de sites de succursales Lync Server à grande échelle

Pour plus d’informations, reportez-vous à la rubrique [détermination de votre configuration d’infrastructure requise pour Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) dans la documentation de planification.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

