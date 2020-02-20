---
title: 'Lync Server 2013 : solutions de résistance de site de succursale'
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
ms.openlocfilehash: a72d07e1ccdae6c433de92057e6e9414fff20153
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a>Solutions de résistance de site de succursale dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-12-10_

Mettre en œuvre la résistance des sites de succursale pour votre organisation présente des avantages évidents. En particulier, si vous perdez la connexion au site central, les utilisateurs de site de succursale continueront à utiliser le service voix entreprise et la messagerie vocale (si vous configurez les paramètres de réacheminement de la messagerie vocale ; pour plus d’informations, consultez la rubrique [Configuration requise pour la résistance des sites de succursale pour Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)). Cependant, pour les sites comportant moins de 25 utilisateurs une solution de résistance peut ne pas être assez rentable.

Si vous décidez de mettre en œuvre la résistance pour les sites de succursale, vous disposez de trois options. Le tableau suivant peut vous aider à déterminer l’option appropriée.

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
<td><p>Hébergez entre 25 et 1 000 utilisateurs sur le site de succursale, et si un déploiement complet n’est pas rentable ou si vous ne disposez pas d’un support d’administration local</p></td>
<td><p>Survivable Branch Appliance</p>
<p>Le Survivable Branch Appliance est un serveur lame standard avec un serveur de médiation et de serveur d’inscriptions Lync Server s’exécutant sur Windows Server 2008 R2. Le Survivable Branch Appliance contient également une passerelle RTC (réseau téléphonique commuté). Des périphériques tiers qualifiés (développés par les partenaires de Microsoft dans le programme de qualification/certification Survivable Branch Appliance (SBA)) assurent une connexion PSTN continue en cas de panne du WAN, mais ils ne fournissent pas de services de conférence et de présence résistants, car ces fonctionnalités dépendent des serveurs frontaux du site central.</p>
<p>Pour plus d’informations sur Survivable Branch Appliances, voir &quot;Survivable Branch&quot; Appliance Details, plus loin dans cette rubrique.</p>
<p><strong>Remarque :</strong> Si vous décidez d’utiliser également une jonction SIP avec votre Survivable Branch appliance, contactez votre fournisseur Survivable Branch Appliance pour en savoir plus sur le fournisseur de services qui convient le mieux à votre organisation.</p></td>
</tr>
<tr class="even">
<td><p>Hôte entre 1000 et 2000 utilisateurs sur votre site de succursale, absence de connexion WAN fiable et disponibilité des administrateurs Lync Server formés</p></td>
<td><p>Survivable Branch Server ou deux Survivable Branch Appliances.</p>
<p>Le Survivable Branch Server est une configuration matérielle requise pour une réunion Windows Server sur lequel le logiciel de serveur d’inscriptions et de médiation Lync Server est installé. Il doit se connecter à une passerelle PSTN ou à une jonction SIP à un fournisseur de services téléphoniques.</p>
<p>Pour plus d’informations sur les serveurs Survivable &quot;Branch Server, voir Survivable&quot; Branch Server Details, plus loin dans cette rubrique.</p></td>
</tr>
<tr class="odd">
<td><p>Si vous avez besoin de fonctionnalités de présence et de conférence en plus des fonctionnalités vocales pour un maximum de 5000 utilisateurs et que des administrateurs Lync Server formés sont disponibles ;</p></td>
<td><p>Procédez à un déploiement de site central avec un serveur Standard Edition au lieu d’un déploiement de site de succursale.</p>
<p>Un déploiement Lync Server complet offre une connexion RTC continue et une présence et une conférence résistantes en cas de panne de réseau étendu (WAN).</p>
<p>Pour plus d’informations sur la préparation de cette solution, reportez-vous à la rubrique <a href="lync-server-2013-planning-for-your-organization.md">Organization Planning for Lync server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Determining Your System Requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Determining Your infrastructure requirements for Lync Server 2013</a>, et d’autres sections pertinentes de la documentation de planification.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a>Topologies résistantes

La figure suivante montre les topologies recommandées pour la résistance des sites de succursale.

**Options de résistance pour sites de succursale**

![Options de résistance des succursales vocales](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Options de résistance des succursales vocales")

</div>

<div>

## <a name="survivable-branch-appliance-details"></a>Survivable Branch Appliance en détail

Le Survivable Branch Appliance Lync Server inclut les composants suivants :

  - un serveur d’inscriptions pour l’authentification et l’inscription des utilisateurs, et le routage des appels ;

  - un serveur de médiation pour la signalisation entre le serveur d’inscriptions et la passerelle PSTN ;

  - une passerelle PSTN pour le routage des appels vers le PSTN comme moyen de transport secondaire en cas de panne du WAN ;

  - SQL Server Express pour le stockage local des données d’utilisateur.

Le Survivable Branch Appliance inclut également des jonctions PSTN, des ports analogiques et une carte Ethernet.

Si la connexion WAN du site de succursale à un site central devient indisponible, les utilisateurs de la succursale peuvent continuer à être enregistrés auprès du serveur Survivable Branch appliance et obtenir des services vocaux ininterrompus à l’aide de la connexion Survivable Branch appliance. au réseau téléphonique commuté (RTC). De même, les utilisateurs du site de succursale se connectant de leur domicile ou d’autres emplacements distants pourront s’enregistrer avec un serveur d’inscriptions du site central si la liaison WAN vers le site de succursale est indisponible. Ces utilisateurs disposeront de la fonctionnalité de communication unifiée complète, la seule exception étant que les appels entrants vers le site de succursale seront transmis à la messagerie vocale. Lorsque la connexion WAN redevient disponible, les utilisateurs du site de succursale disposent de nouveau des fonctionnalités complètes de communication. Ni le basculement vers le Survivable Branch Appliance ni la restauration du service ne nécessitent la présence d’un administrateur informatique.

Lync Server prend en charge jusqu’à deux Survivable Branch appliance sur un site de succursale.

<div>


> [!NOTE]  
> Les utilisateurs hébergés sur une appliance Survivable Branch Lync Server ne peuvent pas créer de nouvelles salles de conversation ni afficher la carte de salle pour les salles existantes.



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a>Vue d’ensemble du déploiement du Survivable Branch Appliance

Le Survivable Branch Appliance est fabriqué par les fabricants d’équipements d’origine en partenariat avec Microsoft et déployés pour leur compte par des détaillants à valeur ajoutée. Ce déploiement ne doit avoir lieu qu’une fois que Lync Server a été déployé sur le site central, une connexion WAN au site de succursale est en place et les utilisateurs de site de succursale sont activés pour voix entreprise.

Pour plus d’informations sur ces phases, voir [Deploying a Survivable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) dans la documentation de déploiement.


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
<td><p>Configurer les services de domaine Active Directory pour le Survivable Branch Appliance</p></td>
<td><p><strong>Sur le site central :</strong></p>
<ol>
<li><p>Créez un compte d’utilisateur de domaine (ou une identité d’entreprise) pour le technicien qui installera et activera le Survivable Branch appliance sur le site de succursale.</p></li>
<li><p>Créez un compte d’ordinateur (avec le nom de domaine complet applicable) pour Survivable Branch Appliance dans les services de domaine Active Directory.</p></li>
<li><p>Dans le générateur de topologies, créez et publiez le Survivable Branch appliance.</p></li>
</ol></td>
<td><p>Le compte d’utilisateur du technicien doit être membre du groupe RTCUniversalSBATechnicians. Le Survivable Branch appliance doit appartenir au groupe RTCSBAUniversalServices, qui se produit automatiquement lorsque vous utilisez le générateur de topologie.</p></td>
</tr>
<tr class="even">
<td><p>Installez et activez le Survivable Branch appliance.</p></td>
<td><p><strong>Sur le site de succursale :</strong></p>
<ol>
<li><p>Connectez le Survivable Branch appliance à un port Ethernet et un port PSTN.</p></li>
<li><p>Démarrez le Survivable Branch appliance.</p></li>
<li><p>Rejoignez le Survivable Branch Appliance au domaine à l’aide du compte d’utilisateur de domaine créé pour le Survivable Branch appliance sur le site central. Définissez le nom de domaine complet et l’adresse IP de sorte qu’ils correspondent au nom de domaine complet créé pour le compte d’utilisateur.</p></li>
<li><p>Configurez le Survivable Branch appliance à l’aide de l’interface utilisateur OEM.</p></li>
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

Dans le générateur de topologies, créez le site de succursale, ajoutez le serveur Survivable Branch Server à ce site, puis exécutez l’Assistant Déploiement de Lync Server sur l’ordinateur sur lequel vous souhaitez installer le rôle.

</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Déploiement de Microsoft Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

