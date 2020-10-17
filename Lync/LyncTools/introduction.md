---
title: Introduction
description: Mise.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb847c499bde077ccaf2aa050de801ceeedcc6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565280"
---
# <a name="introduction"></a>Introduction

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-24_

L’outil de contrainte et de performances de Lync Server 2013 (appelé LyncPerfTool) peut simuler la charge utilisateur des types suivants :


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
<td><p>Conférence client Web Access</p></td>
<td><p>Microsoft Lync 2013 attendant</p></td>
</tr>
<tr class="even">
<td><p>Groupes Response Group</p></td>
<td><p>Développement de la liste de distribution</p></td>
</tr>
<tr class="odd">
<td><p>Requête de téléchargement du carnet d’adresses et de carnet d’adresses</p></td>
<td><p>Enhanced 9-1-1 (E9-1-1) calls and location Profile (plan de numérotation)</p></td>
</tr>
<tr class="even">
<td><p>La</p></td>
<td><p>Affichage de plusieurs flux à partir d’une conférence</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


L’outil de contrainte et de performances de Lync Server 2013 prend en charge la génération de charge et la Fédération entre les pools via une configuration avancée uniquement.

L’outil ne simule pas non plus la charge utilisateur pour les clients suivants :

  - Office Live Meeting 2007

  - Lync 2013 conversation permanente

Par conséquent, l’outil de contrainte et de performances de Lync Server 2013 ne prend pas en charge le test des composants suivants :

  - Lync 2013 conversation permanente

  - Scénarios d’intégration Exchange

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a>Applications et fichiers inclus avec l’outil de contrainte et de performances de Lync Server 2013

Les applications suivantes sont incluses dans l’outil de contrainte et de performances de Lync Server 2013 :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Outil</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UserProvisioningTool.exe</p></td>
<td><p>Outil de mise en service utilisateur Lync Server 2013. Cet outil permet de créer des utilisateurs et des contacts.</p></td>
</tr>
<tr class="even">
<td><p>UserProfileGenerator.exe</p></td>
<td><p>L’outil de configuration de chargement Lync Server 2013. Cet outil permet de configurer les caractéristiques de la charge utilisateur à simuler.</p></td>
</tr>
<tr class="odd">
<td><p>LyncPerfTool.exe</p></td>
<td><p>L’outil de contrainte et de performances de Lync Server 2013. LyncPerfTool est l’outil qui simule la charge utilisateur.</p></td>
</tr>
<tr class="even">
<td><p>Default. TMX</p></td>
<td><p>Default. TMX est requis pour utiliser l’outil de journalisation Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>Exemple de scripts de mise en service</p></td>
<td><p>Ces exemples permettent de configurer la topologie pour exécuter des tests de charge, en fonction de scénarios spécifiques.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

