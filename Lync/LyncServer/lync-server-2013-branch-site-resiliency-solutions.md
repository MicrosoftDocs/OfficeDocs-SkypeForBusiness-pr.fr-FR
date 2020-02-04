---
title: 'Lync Server 2013 : Solutions de résistance de sites de succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16261d4add87462991c877e85cc6a0ff1e7fdfd4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a>Solutions de résistance de sites de succursale dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-12-10_

Mettre en œuvre la résistance des sites de succursale pour votre organisation présente des avantages évidents. En particulier, si vous perdez la connexion au site central, les utilisateurs du site de succursale continuent d’avoir accès à la messagerie vocale et aux services vocaux d’entreprise (si vous configurez les paramètres de reroutage de la messagerie vocale ; pour plus d’informations, voir [Configuration requise pour la résilience de sites de succursale pour Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)). Cependant, pour les sites comportant moins de 25 utilisateurs, une solution de résistance peut ne pas être assez rentable.

Si vous décidez de mettre en œuvre la résistance pour les sites de succursale, vous disposez de trois options. Le tableau ci-dessous peut vous aider à déterminer l’option appropriée.

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Si vous…</th>
<th>Nous vous recommandons d’utiliser un…</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Hébergez entre 25 et 1 000 utilisateurs sur le site de succursale, et si un déploiement complet n’est pas rentable ou si vous ne disposez pas d’une prise en charge d’administration locale.</p></td>
<td><p>Survivable Branch Appliance</p>
<p>L’application branche Survivable est un serveur de Blades standard doté d’un serveur d’archivage et de médiation Lync Server s’exécutant sur Windows Server 2008 R2. L’unité de branchement Survivable comporte également une passerelle RTC (réseau téléphonique commuté). Des périphériques tiers qualifiés (développés par les partenaires de Microsoft dans le programme de qualification/certification Survivable Branch Appliance (SBA) assurent une connexion PSTN continue en cas de panne du réseau étendu, mais ils ne fournissent pas de services de conférence et de présence résistants, car ces fonctionnalités dépendent des serveurs frontaux du site central.</p>
<p>Pour plus d’informations sur les appareils de branche &quot;survivables, voir détails sur&quot; le périphérique de branchement survivant plus loin dans cette rubrique.</p>
<p><strong>Remarque :</strong> Si vous décidez également d’utiliser une ligne SIP avec votre appareil de branchement survivant, contactez le fournisseur de votre application pour savoir quel fournisseur de services est le plus approprié pour votre organisation.</p></td>
</tr>
<tr class="even">
<td><p>Héberger entre 1000 et 2000 sur votre site de succursale, ne pas disposer d’une connexion WAN fiable et avoir reçu des administrateurs Lync Server</p></td>
<td><p>Serveur de succursales survivant ou deux dispositifs de branchement plus survivant.</p>
<p>Le serveur de succursales Survivables est une configuration matérielle requise pour la réunion Windows Server sur laquelle sont installés les logiciels serveur Bureau d’enregistrement et médiation de Lync Server. Il doit se connecter à une passerelle PSTN ou à une jonction SIP à un fournisseur de services téléphoniques.</p>
<p>Pour plus d’informations sur les serveurs de succursales Survivables, voir &quot;détails&quot; sur le serveur de succursales survivant plus loin dans cette rubrique.</p></td>
</tr>
<tr class="odd">
<td><p>Si vous avez besoin de fonctionnalités de présence et de conférence en plus des fonctionnalités vocales pour les utilisateurs de 5000 et que vous disposez d’un administrateur Lync Server expérimenté</p></td>
<td><p>Procédez à un déploiement de site central avec un serveur Standard Edition au lieu d’un déploiement de site de succursale.</p>
<p>Le déploiement de Lync Server à une échelle complète fournit une connexion RTC continue et une présence et une audioconférence résilientes en cas de panne du réseau étendu.</p>
<p>Pour plus d’informations sur la préparation de cette solution, voir <a href="lync-server-2013-planning-for-your-organization.md">planification de l’Organisation pour Lync server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">déterminer la configuration système requise pour Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">déterminer la configuration requise pour votre infrastructure pour Lync Server 2013</a>, et les autres sections pertinentes de la documentation de planification.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a>Topologies résistantes

La figure suivante montre les topologies recommandées pour la résistance des sites de succursale.

**Options de résistance pour sites de succursale**

![Options de résilience de la succursale vocale](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Options de résilience de la succursale vocale")

</div>

<div>

## <a name="survivable-branch-appliance-details"></a>Survivable Branch Appliance en détail

L’application de succursales survivant du serveur Lync inclut les éléments suivants :

  - serveur d’inscriptions pour l’authentification et l’inscription des utilisateurs et routage des appels ;

  - serveur de médiation pour la signalisation entre le serveur d’inscriptions et la passerelle PSTN ;

  - passerelle PSTN pour le routage des appels vers le PSTN comme moyen de transport secondaire en cas de panne du réseau étendu ;

  - SQL Server Express pour le stockage local des données d’utilisateur.

L’unité de branchement Survivable inclut également des Trunks RTC, des ports analogiques et une carte Ethernet.

Si la connexion WAN d’un site de succursale à un site central devient indisponible, les utilisateurs de succursales internes continuent d’être enregistrés auprès du Bureau d’enregistrement d’appliances Survivables et de bénéficier d’un service vocal ininterrompu à l’aide de la connexion de l’appareil de branchement survivant. sur PSTN. De même, les utilisateurs du site de succursale se connectant de leur domicile ou d’autres emplacements distants pourront s’enregistrer avec un serveur d’inscriptions du site central si la liaison de réseau étendu vers le site de succursale est indisponible. Ces utilisateurs disposeront de la fonctionnalité de communication unifiée complète, la seule exception étant que les appels entrants vers le site de succursale seront transmis à la messagerie vocale. Lorsque la connexion de réseau étendu redevient disponible, les utilisateurs du site de succursale disposent de nouveau des fonctionnalités complètes de communication. Par ailleurs, le basculement vers l’appareil de branchement survivant ou la restauration du service nécessite la présence d’un administrateur informatique.

Lync Server prend en charge jusqu’à deux appareils de succursales survivant sur un site de succursale.

<div>


> [!NOTE]  
> Les utilisateurs qui sont hébergés sur une unité de branchement Survivable Lync Server ne peuvent pas créer de nouvelles salles de conversation ou afficher la carte de la salle pour les salles existantes.



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a>Vue d’ensemble du déploiement du Survivable Branch Appliance

Le matériel de branchement survivant est fabriqué par des fabricants d’équipements d’origine en partenariat avec Microsoft et déployés en leur nom par des détaillants à la valeur. Ce déploiement ne doit se produire qu’après le déploiement de Lync Server sur le site central, une connexion WAN au site de succursale est en place, et les utilisateurs du site de succursale activés pour Enterprise Voice.

Pour plus d’informations sur ces étapes, reportez-vous à la rubrique [déploiement d’une unité ou d’un serveur à l’aide de Lync server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) dans la documentation de déploiement.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Étapes</th>
<th>Droits d’utilisateur</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configurer les services de domaine Active Directory pour l’unité de branchement Survivable</p></td>
<td><p><strong>Sur le site central :</strong></p>
<ol>
<li><p>Créer un compte d’utilisateur de domaine (ou une identité d’entreprise) pour le technicien qui installera et activer l’unité de branchement survivant sur le site de la succursale.</p></li>
<li><p>Créer un compte d’ordinateur (à l’aide du nom de domaine complet (FQDN, Fully Qualified Domain Name) pour l’appareil de succursale Survivable dans les services de domaine Active Directory (AD DS).</p></li>
<li><p>Dans le générateur de topologie, créez et publiez l’appareil de branchement survivant.</p></li>
</ol></td>
<td><p>Le compte d’utilisateur du technicien doit être membre du groupe RTCUniversalSBATechnicians. L’unité de branchement survivant doit appartenir au groupe RTCSBAUniversalServices, qui se produit automatiquement lorsque vous utilisez le générateur de topologie.</p></td>
</tr>
<tr class="even">
<td><p>Installez et activez l’unité de branchement Survivable.</p></td>
<td><p><strong>Sur le site de succursale :</strong></p>
<ol>
<li><p>Connectez l’unité de branchement survivant à un port Ethernet et un port PSTN.</p></li>
<li><p>Démarrez l’unité de branchement Survivable.</p></li>
<li><p>Rejoignez l’unité de branchement Survivable au domaine, en utilisant le compte d’utilisateur de domaine créé pour l’unité de branchement survivant sur le site central. Définissez le nom de domaine complet et l’adresse IP de sorte qu’ils correspondent au nom de domaine complet créé pour le compte d’utilisateur.</p></li>
<li><p>Configurez l’unité de branchement Survivable à l’aide de l’interface utilisateur OEM.</p></li>
<li><p>Testez la connectivité PSTN.</p></li>
</ol></td>
<td><p>Le compte d’utilisateur du technicien doit être membre du groupe RTCUniversalSBATechnicians.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a>Serveur Survivable Branch Server en détail

Dans le générateur de topologie, créez le site de succursale, ajoutez le serveur de succursales survivant à ce site, puis exécutez l’Assistant Déploiement de Lync Server sur l’ordinateur sur lequel vous voulez installer le rôle.

</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

