---
title: 'Lync Server 2013 : Liste de vérification du déploiement pour le contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dd425d53a282cc24fed8ad2f8be9acc5bf42209
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a>Liste de vérification du déploiement pour le contrôle d’admission des appels dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-08_

Pour planifier efficacement le contrôle d’admission des appels, vous devez tenir compte des éléments suivants:

  - Conditions préalables pour le déploiement de CAC.

  - Informations requises pour les décisions CAC et de configuration que vous devez effectuer avant le déploiement.

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a>Prérequis de déploiement pour le contrôle d’admission des appels

Avant de déployer le contrôle d’admission des appels, vous devez déjà avoir déployé vos serveurs internes Lync Server 2013, y compris un pool frontal ou un serveur Standard Edition Server.

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a>Exigences en matière de contrôle d’admission des appels

Le tableau suivant récapitule les informations requises pour le déploiement du contrôle d’admission des appels.

### <a name="information-requirements-for-call-admission-control-deployment"></a>Exigences relatives aux informations pour le déploiement de contrôles d’admission des appels

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Information</th>
<th>Résumé des informations requises</th>
<th>Documentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Fonctionnalités du serveur Lync requises par votre organisation</p></td>
<td><ul>
<li><p>Fonctionnalités devant être prises en charge par votre organisation</p></li>
<li><p>Fonctionnalités à activer pour les utilisateurs individuels</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Définition de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Topologies et composants à déployer</p></td>
<td><ul>
<li><p>Les composants liés au CAC sont automatiquement installés dans le cadre de Lync Server 2013</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Définition de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configuration système requise</p></td>
<td><ul>
<li><p>Configuration matérielle requise</p></li>
<li><p>Configuration logicielle requise</p></li>
<li><p>Exigences en matière de colocalisation</p></li>
</ul></td>
<td><p><a href="lync-server-2013-determining-your-system-requirements.md">Détermination de la configuration système requise pour Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Conditions d’infrastructure requises</p></td>
<td><ul>
<li><p>Aucun besoin d’infrastructure spécifique n’est nécessaire pour le CAC</p></li>
</ul></td>
<td><p><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Configuration requise pour l’infrastructure pour le contrôle d’admission des appels dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Exigences relatives à l’interface réseau</p></td>
<td><ul>
<li><p>Informations d’interface interne et externe</p></li>
<li><p>Informations de routage (y compris les informations sur le <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>blog nexthop à partir du canal de réponse client de l’équipe Microsoft Lync Server)</p></li>
</ul></td>
<td><p><a href="lync-server-2013-deploying-external-user-access.md">Déploiement de l’accès des utilisateurs externes dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Stratégie de déploiement</p></td>
<td><ul>
<li><p>Séquence de déploiement</p></li>
<li><p>Groupe de travail ou domaine</p></li>
<li><p>Sécurité</p></li>
<li><p>Surveillance et audit</p></li>
<li><p>Considérations en matière de matériel</p></li>
</ul></td>
<td><p><a href="lync-server-2013-best-practices-for-call-admission-control.md">Meilleures pratiques liées au contrôle d’admission des appels dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Processus de déploiement</p></td>
<td><ul>
<li><p>Conditions requises</p></li>
<li><p>Exigences relatives aux informations</p></li>
<li><p>Processus et procédures</p></li>
</ul></td>
<td><p><a href="lync-server-2013-configure-call-admission-control.md">Configurer le contrôle d’admission des appels dans Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

