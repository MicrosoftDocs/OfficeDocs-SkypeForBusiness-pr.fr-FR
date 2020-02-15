---
title: 'Lync Server 2013 : configuration requise pour la résistance des sites de succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 563179eb5933a6f2c1ab996fb1e20c7b047a2ae3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a>Configuration requise pour la résistance des sites de succursale pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-25_

Cette rubrique a pour but de vous aider à préparer les utilisateurs à la résistance des sites de succursale et à la survivabilité de la messagerie vocale, et indique également les configurations matérielles et logicielles correspondantes requises.

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a>Préparation des utilisateurs de succursale à la résistance des sites de succursale

Préparez les utilisateurs à la résistance des sites de succursale en définissant leur pool de serveurs d’inscriptions comme étant le Survivable Branch Appliance (SBA) ou le serveur Survivable Branch Server.

<div>

## <a name="registrar-assignments-for-branch-users"></a>Assignations de serveurs d’inscriptions aux utilisateurs de succursale

Quelle que soit la solution de résistance de site de succursale que vous choisissez, vous devrez affecter un serveur d’inscriptions principal à chaque utilisateur. Les utilisateurs de site de succursale doivent toujours s’inscrire auprès du serveur d’inscriptions sur le site de succursale, que ce serveur d’inscriptions réside dans le Survivable Branch appliance, le serveur Survivable Branch Server ou le serveur autonome Lync Server 2013 ou Enterprise Edition. Un enregistrement de ressource de service (SRV) DNS (Domain Name System) est requis pour qu’un client puisse détecter automatiquement son pool de serveurs d’inscriptions. Si le Survivable Branch Appliance devient indisponible, les clients du site de succursale découvrent automatiquement le serveur d’inscriptions de sauvegarde.

Si un site de succursale ne dispose pas d’un serveur DNS, il existe deux autres façons de configurer la découverte du Survivable Branch Appliance ou du serveur Survivable Branch Server :

  - Configurez l’option DHCP 120 sur le serveur DHCP (Dynamic Host Configuration Protocol) du site de succursale pour qu’elle pointe vers le nom de domaine complet (FQDN) du Survivable Branch Appliance ou du serveur Survivable Branch Server.

  - Configurez le Survivable Branch Appliance ou le serveur Survivable Branch Server pour répondre aux requêtes DHCP 120.

</div>

<div>

## <a name="voice-routing-for-branch-users"></a>Routage des communications vocales des utilisateurs de succursale

Nous vous recommandons de créer une stratégie VoIP (Voice over Internet Protocol) distincte au niveau de l’utilisateur pour les utilisateurs d’un site de succursale. Cette stratégie doit inclure un itinéraire principal qui utilise le Survivable Branch Appliance ou une passerelle de serveur de succursale, ainsi qu’un ou plusieurs itinéraires de sauvegarde qui utilisent une jonction avec une passerelle PSTN (réseau téléphonique commuté) sur le site central. Si l’itinéraire principal n’est pas disponible, l’itinéraire de sauvegarde qui utilise une ou plusieurs passerelles de site central est utilisé à la place. De cette façon, quel que soit l’emplacement d’enregistrement d’un utilisateur, sur le serveur de succursale ou sur le pool de serveurs d’inscriptions de sauvegarde du site central, la stratégie VoIP de l’utilisateur est toujours en vigueur. Il s’agit d’une considération importante pour les scénarios de basculement. Par exemple, si vous devez renommer le Survivable Branch Appliance ou reconfigurer le Survivable Branch Appliance pour qu’il se connecte à un pool de serveurs d’inscriptions de sauvegarde sur le site central, vous devez déplacer les utilisateurs du site de succursale vers le site central pendant toute la durée. (Pour plus d’informations sur la modification du nom ou la reconfiguration d’un Survivable Branch appliance, voir [annexe B : gestion d’un Survivable Branch Appliance dans Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) dans la documentation de déploiement.) Si ces utilisateurs ne disposent pas de stratégies VoIP au niveau utilisateur ou de plans de numérotation au niveau de l’utilisateur, lorsque les utilisateurs sont déplacés vers un autre site, les stratégies VoIP au niveau du site et les plans de numérotation au niveau du site du site central s’appliquent par défaut aux utilisateurs, et non aux stratégies VoIP et aux plans de numérotation du site de succursale Dans ce scénario, sauf si les stratégies VoIP au niveau du site et les plans de numérotation au niveau du site utilisés par le pool de serveurs d’inscriptions de sauvegarde peuvent également s’appliquer aux utilisateurs du site de succursale, leurs appels échouent. Par exemple, si des utilisateurs d’un site de succursale situé au Japon sont déplacés vers un site central à Redmond, un plan de numérotation avec des règles de normalisation qui précèdent + 1425 à tous les appels à 7 chiffres est peu susceptible de traduire correctement les appels pour ces utilisateurs.

<div>


> [!IMPORTANT]  
> Lorsque vous créez un itinéraire alternatif de succursale, nous vous conseillons d’ajouter deux enregistrements d’utilisation téléphonique PSTN à la stratégie utilisateur de succursale et d’assigner des itinéraires séparés à chacun d’entre eux. Le premier itinéraire, ou principal, achemine les appels vers la passerelle associée au Survivable Branch Appliance (SBA) ou au serveur de succursale ; la deuxième ou la sauvegarde de l’itinéraire dirige les appels vers la passerelle sur le site central. En dirigeant les appels, le SBA ou le serveur de succursale tente tous les itinéraires assignés au premier enregistrement d’utilisation PSTN avant d’essayer le deuxième enregistrement.



</div>

Pour garantir que les appels entrants vers les utilisateurs de sites de succursale atteindront ces utilisateurs lorsque la passerelle de succursale ou le composant Windows du serveur Survivable Branch Appliance est indisponible (ce qui se produit, par exemple, si le Survivable Branch Appliance ou Branch. la passerelle n’était plus disponible pour la maintenance), créez un itinéraire de basculement sur la passerelle (ou travaillez avec votre fournisseur de serveurs d’inscriptions directe) pour rediriger les appels entrants vers le pool de serveurs d’inscriptions de sauvegarde sur le site central. À partir de là, les appels sont routés sur la liaison de réseau étendu (WAN) en direction des utilisateurs de succursale. Assurez-vous que l’itinéraire traduit les numéros selon les formats de numéro de téléphone acceptés par la passerelle PSTN ou un autre homologue de jonction. Pour plus d’informations sur la création d’un itinéraire de basculement, voir [configuration d’un itinéraire de basculement dans Lync Server 2013](lync-server-2013-configuring-a-failover-route.md). De même, créez des plans de numérotation au niveau du service pour la jonction associée à la passerelle du site de succursale afin de normaliser les appels entrants. Si vous avez deux Survivable Branch Appliances sur un site de succursale, vous pouvez créer un plan de numérotation au niveau du site pour les deux, sauf si un plan de niveau de service distinct est nécessaire.

<div>


> [!NOTE]  
> Pour calculer la consommation des ressources du site central par les utilisateurs de site de succursale qui recourent au site central pour accéder aux fonctionnalités de présence, de conférence ou de basculement, nous vous conseillons de considérer chaque utilisateur de site de succursale comme s’il était inscrit sur le site central. Il n’existe actuellement aucune limite au nombre d’utilisateurs de site de succursale, y compris les utilisateurs enregistrés avec un Survivable Branch appliance.



</div>

Nous vous recommandons également de créer un plan de numérotation et une stratégie de voix au niveau utilisateur, et de les affecter aux utilisateurs de site de succursale. Pour plus d’informations, reportez-vous à la rubrique [Create a dial plan in Lync server 2013](lync-server-2013-create-a-dial-plan.md) et [Create the VoIP Routing Policy for Branch users in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) dans la documentation de déploiement.

<div>

## <a name="routing-extension-numbers"></a>Acheminement des numéros de poste

Lors de la préparation des plans de numérotation et des stratégies de voix pour les utilisateurs de site de succursale, n’oubliez pas d’inclure des règles de normalisation et des règles de conversion qui correspondent aux chaînes et au format de nombre utilisés dans l’attribut msRTCSIP-Line (ou URI de ligne), afin que Lync 2013 appelle activé entre les succursales les utilisateurs du site et les utilisateurs du site central sont routés correctement, en particulier lorsque les appels doivent être réacheminés via le réseau téléphonique commuté car la liaison de réseau étendu n’est pas disponible. D’autres éléments particuliers sont à prendre en considération dans le cas des numéros composés qui incluent des numéros de poste et non simplement des numéros de téléphone.

Les règles de normalisation et de traduction qui correspondent à des URI de ligne contenant un numéro de poste, seul ou en plus d’un numéro de téléphone E.164 complet, imposent des exigences supplémentaires. Cette section décrit plusieurs exemples de scénarios pour acheminer les appels pour des URI de ligne constitués d’un numéro de poste.

Si votre organisation n’a pas de numéros de téléphone SDA (Sélection directe à l’arrivée) configurés pour les utilisateurs et que l’URI de ligne de chaque utilisateur est configuré avec *uniquement* un numéro de poste, les utilisateurs internes peuvent s’appeler en composant uniquement le numéro de poste. Toutefois, vous devez configurer des règles de normalisation qui puissent s’appliquer aux appels d’un utilisateur d’un site de succursale à destination d’un utilisateur du site central qui correspondent aux numéros de poste.

Dans un scénario où la liaison de réseau étendu entre un site de succursale et un site central est disponible, les appels des utilisateurs du site de succursale à destination des utilisateurs du site central ne nécessitent pas de règle de normalisation correspondante pour traduire le numéro, car l’appel n’est pas acheminé sur le réseau téléphonique commuté. Par exemple :


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
<td><p>Ne traduit pas les numéros à 5 chiffres</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>$1</p></td>
<td><p>10001 n’est pas traduit</p></td>
</tr>
</tbody>
</table>


Vous devez également faire face aux scénarios de numéros de poste spécifiques où la liaison de réseau étendu entre un site de succursale et un site central n’est pas disponible et où un appel émanant d’un site de succursale doit être acheminé sur le réseau téléphonique commuté. En cas de panne de réseau étendu, si l’utilisateur d’un site de succursale appelle un utilisateur du site central en composant uniquement le numéro de poste de ce dernier, vous devez disposer d’une règle de traduction sortante qui ajoute le numéro de téléphone complet de l’utilisateur du site central. Si l’URI de ligne d’un utilisateur contient le numéro de téléphone complet de votre organisation et le numéro de poste unique de l’utilisateur au lieu d’un numéro de téléphone complet propre à l’utilisateur, vous devez disposer d’une règle de traduction sortante qui ajoute le numéro de téléphone complet de l’organisation. Par exemple :


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
<td><p>+ 14255550123 ; EXT = $1</p></td>
<td><p>10001 devient +14255550123;ext=10001</p></td>
</tr>
<tr class="even">
<td><p>Traduit les numéros à 5 chiffres en numéro de téléphone de votre organisation complété du poste d’un utilisateur</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>+ 14255550100 ; EXT = $1</p></td>
<td><p>10001 devient +14255550100;ext=10001</p></td>
</tr>
</tbody>
</table>


Dans ce scénario, si l’homologue de jonction qui traite le réacheminement vers le réseau téléphonique commuté ne prend pas en charge les numéros de poste, la règle de traduction sortante doit également supprimer le numéro de poste. Par exemple :


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
<td><p>+ $1</p></td>
<td><p>+14255550123;ext=10001 devient +14255550123</p></td>
</tr>
</tbody>
</table>


Qu’une liaison de réseau étendu soit disponible ou pas, si votre organisation n’a pas de numéros SDA configurés pour les utilisateurs individuels et que l’URI de ligne d’un utilisateur contient le numéro de téléphone de votre organisation et le numéro de poste unique de l’utilisateur, vous devez configurer l’URI de ligne du numéro de téléphone de votre organisation avec un numéro joignable pour l’homologue de jonction ou la passerelle PSTN du site de succursale. Vous devez également configurer l’URI de ligne du numéro de téléphone de votre organisation de sorte qu’il contienne son propre poste unique pour les appels devant être acheminés vers ce numéro.

Pour plus d’informations sur les appels d’un utilisateur de site central vers un utilisateur de site de succursale lorsque la liaison de réseau étendu entre les deux sites n’est pas disponible, voir la section « Préparation à la survivabilité de la messagerie vocale » plus loin dans cette rubrique. Pour plus d’informations sur les plans de numérotation et les règles de normalisation, y compris d’autres exemples de règles, voir [Dial plans and Normalization Rules in Lync server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) dans la documentation de planification et [Configuring Dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) dans la documentation de déploiement. Pour plus d’informations sur les règles de traduction sortante, voir [règles de conversion dans Lync server 2013](lync-server-2013-translation-rules.md) dans la documentation de planification et [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a>Préparation de la survavibilité de la messagerie vocale

La messagerie unifiée Exchange est généralement installée uniquement sur un site central et non sur des sites de succursale. Un appelant doit pouvoir laisser un message vocal, même si la liaison de réseau étendu entre un site de succursale et le site central n’est pas disponible. Par conséquent, la configuration de l’URI de ligne pour le numéro de téléphone du standard automatique de messagerie unifiée Exchange qui fournit la messagerie vocale pour les utilisateurs de site de succursale exige des considérations spéciales, ainsi que la stratégie de voix, le plan de numérotation et les règles de normalisation applicables à ce message vocal. valeur.

Survivable Branch Appliances (SBA) et les serveurs Survivable Branch Server offrent une survivabilité de la messagerie vocale pour les utilisateurs de succursale lors d’une panne de réseau étendu. Plus précisément, si vous utilisez un Survivable Branch Appliance ou un serveur Survivable Branch Server et que le réseau étendu devient indisponible, le SBA ou le Survivable Branch Server redirige les appels sans réponse sur le RTC vers la messagerie unifiée Exchange au niveau du site central. Avec un SBA ou un serveur Survivable Branch Server, les utilisateurs peuvent également récupérer des messages vocaux via le RTC lors d’une panne de réseau étendu (WAN). Enfin, pendant une panne de réseau étendu, le Survivable Branch Appliance ou le serveur Survivable Branch Server met en file d’attente les notifications d’appels manqués, puis les télécharge sur le serveur de messagerie unifiée Exchange lors de la restauration du réseau étendu. Pour vous assurer que le reroutage de messagerie vocale est résilient, veillez à ajouter une entrée pour le nom de domaine complet du pool de sites central et une entrée pour le nom de domaine complet du serveur Edge au fichier hosts sur le serveur Survivable Branch Server. À défaut, il est possible que la résolution DNS arrive à expiration si vous ne disposez pas de serveur DNS sur le site de succursale.

Pour configurer la survivabilité de la messagerie vocale pour les utilisateurs de site de succursale, les configurations suivantes sont recommandées :

  - Un administrateur Microsoft Exchange doit configurer le standard automatique de messagerie unifiée Exchange (AA) pour qu’il accepte uniquement les messages. Cette configuration désactive toutes les autres fonctions génériques, comme le transfert à un utilisateur ou un opérateur, et limite le rôle du standard automatique à la seule réception des messages. Sinon, l’administrateur Exchange peut utiliser un standard automatique générique ou personnalisé pour router l’appel vers un opérateur.

  - L’administrateur Lync Server doit prendre le numéro de téléphone AA et utiliser ce numéro de téléphone comme numéro de **standard automatique de messagerie unifiée Exchange** dans les paramètres de réacheminement de la messagerie vocale pour le Survivable Branch Appliance ou le serveur de succursale.

  - L’administrateur Lync Server doit obtenir le numéro de téléphone de l’accès abonné de la messagerie UNIFIÉe Exchange et utiliser ce numéro comme numéro d' **accès abonné** dans les paramètres de réacheminement de la messagerie vocale pour le Survivable Branch Appliance ou le serveur Survivable Branch Server.

  - L’administrateur Lync Server doit configurer la messagerie unifiée Exchange de sorte qu’un seul plan de numérotation soit associé à tous les utilisateurs de succursale qui ont besoin d’accéder à la messagerie vocale pendant une panne de réseau étendu (WAN).

  - Lorsque la liaison de réseau étendu n’est pas disponible, les appels à destination des utilisateurs de site de succursale peuvent être acheminés vers la messagerie vocale de la messagerie unifiée Exchange de l’utilisateur, à condition toutefois que la stratégie de voix appliquée à l’appel spécifie un numéro de téléphone de messagerie vocale unique et qu’elle inclue un numéro de poste.

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Configuration matérielle et logicielle requise pour la résistance des sites de succursale

La configuration matérielle et logicielle requise varie en fonction de la solution de résistance.

<div>

## <a name="requirements-for-survivable-branch-appliances"></a>Configuration requise pour les Survivable Branch Appliances

Le matériel et les logiciels requis sont intégrés dans le Survivable Branch appliance. Cependant, il est également recommandé que chaque site de succursale déploie un serveur DHCP afin d’obtenir des adresses IP du client ; sinon, lorsque le bail DHCP expire, les clients ne disposent plus de connectivité IP.

Si les serveurs DNS d’entreprise se trouvent uniquement dans des sites centraux, les utilisateurs de site de succursale ne pourront pas se connecter à eux lors d’une panne de réseau étendu, et par conséquent, la découverte de Lync Server qui utilise l’enregistrement de ressource SRV (SRV) DNS échouera. Pour garantir un réacheminement rapide lors d’une panne de réseau étendu, les enregistrements DNS doivent être mis en cache au niveau du site de succursale. Si le routeur de succursale prend en charge le cache DNS, activez-le à cette fin. Vous pouvez également déployer un serveur DNS au niveau de la succursale. Il peut s’agir d’un serveur autonome ou d’une version du Survivable Branch appliance qui prend en charge les fonctionnalités DNS. Pour plus d’informations, contactez votre fournisseur Survivable Branch appliance.

<div>


> [!NOTE]  
> Il n’est pas nécessaire de disposer d’un contrôleur de domaine sur un site de succursale. Le Survivable Branch Appliance authentifie les clients à l’aide d’un certificat spécial qui envoie le client en réponse à la demande de certificat du client lorsqu’il se connecte.



</div>

Les clients Lync peuvent découvrir Lync Server à l’aide de l’option DHCP 120 (serveur d’inscriptions SIP). La configuration peut prendre l’une des deux formes suivantes :

  - Configurez le serveur DHCP sur le site de succursale pour répondre aux requêtes DHCP 120, qui renvoient le nom de domaine complet du serveur d’inscriptions sur le Survivable Branch Appliance ou le serveur Survivable Branch Server.

  - Activez le service DHCP Lync Server. Lorsque cette option est activée, le serveur d’inscriptions Lync Server répond aux requêtes DHCP 120. Notez que le serveur d’inscriptions ne répond pas aux requêtes DHCP autres que DHCP, option 120.

De plus, pour les sites de succursale plus importants disposant de plusieurs sous-réseaux, les agents de relais DHCP doivent être activés pour transférer les requêtes DHCP, option 120, au serveur DHCP (configuration 1) ou au serveur d’inscriptions (configuration 2).

Pour finir, les utilisateurs de site de succursale doivent être configurés pour voix entreprise et être mis en service avec un point de terminaison de communications unifiées approprié.

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a>Configuration requise pour les serveurs Survivable Branch Server

La configuration requise pour les serveurs Survivable Branch Server est la même que pour un serveur frontal. Pour plus d’informations, reportez-vous à la rubrique [Server Hardware Platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de planification.

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a>Conditions requise pour les déploiements de sites de succursale Lync Server pleine échelle

Pour plus d’informations, reportez-vous à la rubrique [Determining Your infrastructure Requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) dans la documentation de planification.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

