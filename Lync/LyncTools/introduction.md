---
title: Introduction
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 893205127b6b1ccba958a0882c3aa0d1360a7c06
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction"></a>Introduction

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-24_

L’outil de stress et de performance de Lync Server 2013 (appelé LyncPerfTool) peut simuler la charge utilisateur des types suivants :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Messagerie instantanée et présence</p></td>
<td><p>Audioconférence</p></td>
</tr>
<tr class="even">
<td><p>Partage d'application</p></td>
<td><p>Voix sur IP (VoIP), y compris la simulation de réseau téléphonique commuté (PSTN)</p></td>
</tr>
<tr class="odd">
<td><p>Conférences de clients d’accès Web</p></td>
<td><p>Microsoft Lync 2013 attendant</p></td>
</tr>
<tr class="even">
<td><p>Response Groups</p></td>
<td><p>Extension de liste de distribution</p></td>
</tr>
<tr class="odd">
<td><p>Requête de téléchargement du carnet d’adresses et du carnet d’adresses</p></td>
<td><p>9-1-1 d’amélioration (E9-1-1) : profil d’emplacement et d’emplacement (plan de numérotation)</p></td>
</tr>
<tr class="even">
<td><p>Multivue</p></td>
<td><p>Affichage de plusieurs flux d’une conférence</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


L’outil de stress et de performance de Lync Server 2013 prend en charge la génération et la Fédération par pool via la configuration avancée uniquement.

L’outil ne simule pas non plus la charge des utilisateurs pour les clients suivants :

  - Office Live Meeting 2007

  - Conversation permanente Lync 2013

Par conséquent, l’outil de stress et de performance de Lync Server 2013 ne prend pas en charge le test des composants suivants :

  - Conversation permanente Lync 2013

  - Scénarios d’intégration Exchange

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a>Applications et fichiers inclus dans l’outil de stress et de performance de Lync Server 2013

Les applications suivantes sont incluses dans l’outil de stress et de performance de Lync Server 2013 :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Il</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UserProvisioningTool. exe</p></td>
<td><p>Outil de mise en service des utilisateurs de Lync Server 2013. Cet outil permet de créer des utilisateurs et des contacts.</p></td>
</tr>
<tr class="even">
<td><p>UserProfileGenerator. exe</p></td>
<td><p>Outil de configuration de chargement de Lync Server 2013. Cet outil permet de configurer les caractéristiques de la charge d’utilisateur pour la simulation.</p></td>
</tr>
<tr class="odd">
<td><p>LyncPerfTool. exe</p></td>
<td><p>Outil de stress et de performance de Lync Server 2013. LyncPerfTool est l’outil qui simule la charge utilisateur.</p></td>
</tr>
<tr class="even">
<td><p>Default. TMX</p></td>
<td><p>Default. TMX est requis pour l’utilisation de l’outil de journalisation Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>Exemples de scripts de mise en service</p></td>
<td><p>Ces exemples sont utilisés pour configurer la topologie pour exécuter des tests de charge, en fonction de scénarios spécifiques.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

