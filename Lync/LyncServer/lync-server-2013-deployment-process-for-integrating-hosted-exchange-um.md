---
title: 'Lync Server 2013 : Processus de déploiement pour l’intégration de la messagerie unifiée Exchange hébergée'
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
ms.openlocfilehash: b314ea3bd7a88264a72c804c7c67ed3baa819972
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a>Processus de déploiement pour l’intégration de la messagerie unifiée Exchange hébergée à Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-25_

La planification efficace de l’intégration de Lync Server 2013 à la messagerie unifiée Exchange hébergée (MU) nécessite que vous prenez en compte les éléments suivants :

  - Conditions préalables à l’intégration de Lync Server 2013 avec la messagerie unifiée Exchange hébergée

  - Étapes requises lors du processus d’intégration

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a>Prérequis de déploiement pour l’intégration à la messagerie unifiée Exchange hébergée

Avant de pouvoir commencer le processus d’intégration, vous devez déjà avoir déployé Lync Server 2013 (au minimum, un pool frontal ou un serveur Standard Edition Server), un serveur Edge et des clients Lync 2013 ou Lync 2010.

</div>

<div>

## <a name="integration-process"></a>Processus d’intégration

Le tableau suivant fournit une vue d’ensemble du processus d’intégration d’Exchange UM hébergé. Pour plus d’informations sur les étapes de déploiement, voir [fourniture de messages vocaux aux utilisateurs Lync Server 2013 sur la messagerie unifiée Exchange hébergée](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) dans la documentation de déploiement.


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
<td><p>Configurer le serveur de périphérie</p></td>
<td><ol>
<li><p>Configurez le serveur Edge pour la fédération.</p></li>
<li><p>Répliquer manuellement les données sur le serveur Edge.</p></li>
<li><p>Configurez le fournisseur d’hébergement sur le serveur Edge.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configuration du serveur Edge pour l’intégration à la messagerie unifiée Exchange hébergée</a></p></td>
</tr>
<tr class="even">
<td><p>Configurer une stratégie de messagerie vocale hébergée.</p></td>
<td><ol>
<li><p>Modifiez la stratégie globale de messagerie vocale hébergée ou créez une nouvelle stratégie de messagerie vocale hébergée avec un site ou une étendue par utilisateur.</p></li>
<li><p>Pour les stratégies dont l’étendue est définie par l’utilisateur, affectez la stratégie à des utilisateurs ou des groupes.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Gestion des stratégies de messagerie vocale hébergée dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Autorisez les utilisateurs à utiliser la messagerie vocale hébergée.</p></td>
<td><ul>
<li><p>Configurez des comptes d’utilisateurs pour les utilisateurs dont la boîte aux lettres se trouve sur un service Exchange hébergé.</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Activation des utilisateurs pour la messagerie vocale hébergée dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurer les objets de contact hébergés.</p></td>
<td><ol>
<li><p>Créer des objets de contact de standard automatique pour la messagerie unifiée Exchange hébergée.</p></li>
<li><p>Créer des objets de contact d’accès d’abonné pour la messagerie unifiée Exchange hébergée.</p></li>
</ol></td>
<td><p>RTCUniversalUserAdmins</p>
<div>

> [!NOTE]  
> Pour créer, modifier ou supprimer des objets de contact, l’utilisateur exécutant l’applet de commande New-CsExUmContact, Set-CsExUmContact ou Remove-CsExUmContact doit disposer de l’autorisation appropriée pour l’unité d’organisation Active Directory où les nouveaux objets de contact sont stockés. Cette autorisation peut être accordée en exécutant l’applet de commande Grant-CsOUPermission. Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell.


</div></td>
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Création des objets de contact pour la messagerie unifiée Exchange hébergée dans Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

