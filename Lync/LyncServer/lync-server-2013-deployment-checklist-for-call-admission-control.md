---
title: 'Lync Server 2013 : liste de vérification du déploiement pour le contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13d9591ad8dfed90373fedc8adfb3a3c3c44eb57
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529141"
---
# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a>Liste de vérification du déploiement pour le contrôle d’admission des appels dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-08_

Pour planifier efficacement le service Contrôle d’admission des appels (CAC), vous devez tenir compte :

  - des conditions préalables au déploiement du service Contrôle d’admission des appels (CAC) ;

  - des informations requises pour déployer le service Contrôle d’admission des appels et des décisions de configuration à prendre avant le déploiement ;

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a>Conditions préalables au déploiement du contrôle d’admission des appels

Avant de déployer le contrôle d’admission des appels, vous devez déjà avoir déployé vos serveurs internes Lync Server 2013, y compris un pool frontal ou un serveur Standard Edition.

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a>Informations requises pour le contrôle d’admission des appels

Le tableau suivant résume les informations requises pour le déploiement du service Contrôle d’admission des appels.

### <a name="information-requirements-for-call-admission-control-deployment"></a>Informations requises pour le déploiement du contrôle d’admission des appels

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Informations</th>
<th>Résumé des informations requises</th>
<th>Documentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Fonctionnalités Lync Server requises par votre organisation</p></td>
<td><ul>
<li><p>Fonctionnalités à prendre en charge par votre organisation</p></li>
<li><p>Fonctionnalités à activer pour les utilisateurs individuels</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Définition de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Topologies et composants à déployer</p></td>
<td><ul>
<li><p>Les composants liés au contrôle d’admission des problèmes sont installés automatiquement dans le cadre de Lync Server 2013</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Définition de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configuration système requise</p></td>
<td><ul>
<li><p>Configuration matérielle requise</p></li>
<li><p>Configuration logicielle requise</p></li>
<li><p>Configuration de colocation requise</p></li>
</ul></td>
<td><p><a href="lync-server-2013-determining-your-system-requirements.md">Détermination de la configuration système requise pour Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Conditions d’infrastructure requises</p></td>
<td><ul>
<li><p>Aucune configuration d’infrastructure spécifique n’est requise pour CAC</p></li>
</ul></td>
<td><p><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Configuration requise pour l’infrastructure pour le contrôle d’admission des appels dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Configuration de l’interface réseau requise</p></td>
<td><ul>
<li><p>Informations d’interface interne et externe</p></li>
<li><p>Informations de routage (notamment des informations sur le blog NextHop à l’adresse <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a> , le canal de réponse client de l’équipe Microsoft Lync Server)</p></li>
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
<li><p>Considérations matérielles</p></li>
</ul></td>
<td><p><a href="lync-server-2013-best-practices-for-call-admission-control.md">Meilleures pratiques pour le contrôle d’admission des appels dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Processus de déploiement</p></td>
<td><ul>
<li><p>Conditions préalables</p></li>
<li><p>Informations requises</p></li>
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

