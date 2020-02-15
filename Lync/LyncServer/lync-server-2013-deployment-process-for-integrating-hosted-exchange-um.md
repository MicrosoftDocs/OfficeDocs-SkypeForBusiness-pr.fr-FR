---
title: 'Lync Server 2013 : processus de déploiement pour l’intégration de la messagerie unifiée Exchange hébergée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdab3e470037780d871f9ac6a5eba549497cd23a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a>Processus de déploiement pour l’intégration de la messagerie unifiée Exchange hébergée à Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-25_

Pour une planification efficace de l’intégration de Lync Server 2013 à la messagerie unifiée Exchange hébergée, vous devez tenir compte des éléments suivants :

  - Conditions préalables à l’intégration de Lync Server 2013 avec la messagerie unifiée Exchange hébergée

  - Étapes requises au cours du processus d’intégration

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a>Conditions préalables au déploiement pour l’intégration à la messagerie unifiée Exchange hébergée

Avant de commencer le processus d’intégration, vous devez déjà avoir déployé Lync Server 2013 (au minimum, un pool frontal ou un serveur Standard Edition Server), un serveur Edge et des clients Lync 2013 ou Lync 2010.

</div>

<div>

## <a name="integration-process"></a>Processus d’intégration

Le tableau suivant présente une vue d’ensemble du processus d’intégration de la messagerie unifiée Exchange hébergée. Pour plus d’informations sur les étapes de déploiement, voir la rubrique relative à la [messagerie vocale Exchange hébergée pour les utilisateurs Lync Server 2013](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) dans la documentation de déploiement.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Étapes</th>
<th>Droits et autorisations</th>
<th>Documentation de déploiement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configurez le serveur Edge.</p></td>
<td><ol>
<li><p>Configurez le serveur Edge pour la fédération.</p></li>
<li><p>Répliquez manuellement les données sur le serveur Edge.</p></li>
<li><p>Configurez le fournisseur d’hébergement sur le serveur Edge.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configuration du serveur Edge pour l’intégration à la messagerie unifiée Exchange hébergée</a></p></td>
</tr>
<tr class="even">
<td><p>Configurez la stratégie de messagerie vocale hébergée.</p></td>
<td><ol>
<li><p>Modifiez la stratégie globale de messagerie vocale hébergée ou créez une stratégie de messagerie vocale hébergée avec une étendue de site ou par utilisateur.</p></li>
<li><p>Lorsque les stratégies sont définies avec une étendue par utilisateur, attribuez-les à des utilisateurs ou à des groupes.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Gérer les stratégies de messagerie vocale hébergée dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Activez les utilisateurs pour la messagerie vocale hébergée.</p></td>
<td><ul>
<li><p>Configurez les comptes des utilisateurs qui possèdent des boîtes aux lettres sur un service Exchange hébergé.</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Activer les utilisateurs pour la messagerie vocale hébergée dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurez les objets contact hébergés.</p></td>
<td><ol>
<li><p>Créez des objets contact de standard automatique pour la messagerie unifiée Exchange hébergée.</p></li>
<li><p>Créez des objets contact d’accès abonné pour la messagerie unifiée Exchange hébergée.</p></li>
</ol></td>
<td><p>RTCUniversalUserAdmins</p>
<div>

> [!NOTE]  
> Pour créer, modifier ou supprimer des objets contact, l’utilisateur qui exécute la cmdlet New-CsExUmContact, Set-CsExUmContact ou Remove-CsExUmContact doit posséder l’autorisation appropriée sur l’unité d’organisation Active Directory où sont stockés les nouveaux objets contact. Cette autorisation peut être accordée en exécutant la cmdlet Grant-CsOUPermission. Pour plus d’informations, voir la documentation Lync Server Management Shell.


</div></td>
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Créer des objets contact pour la messagerie unifiée Exchange hébergée dans Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

