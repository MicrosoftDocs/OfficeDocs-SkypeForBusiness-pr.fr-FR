---
title: 'Lync Server 2013 : vue d’ensemble des scénarios de création de flux de travail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of workflow creation scenarios
ms:assetid: 05e0c175-0f1a-4bb1-b048-c68584d00649
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204646(v=OCS.15)
ms:contentKeyID: 48183309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27383db13176150078bf4855dee4df57cb1615af
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41989879"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-workflow-creation-scenarios-in-lync-server-2013"></a>Vue d’ensemble des scénarios de création de flux de travail dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-17_

Lorsque vous créez des flux de travail, deux scénarios sont possibles :

  - **L’administrateur crée et configure le flux de travail** — Le membre du rôle CsResponseGroupAdministrator (ou équivalent) crée et active le flux de travail et tous les éléments dans le flux de travail, tels que les groupes d’agents, les files d’attente, les congés et les heures ouvrées, la musique d’attente, etc.

  - **L’administrateur crée le flux de travail et le responsable configure les options** — Le membre du rôle CsResponseGroupAdministrator (ou équivalent) définit l’URI SIP principal et le nom complet, affecte des membres du rôle CsResponseGroupManager, sélectionne une file d’attente et active le flux de travail. Le membre du rôle CsResponseGroupManager peut alors ouvrir une session et modifier la configuration du flux de travail en créant des groupes d’agents. Il affecte également le groupe à la file d’attente, configure le numéro de téléphone, les congés et les heures ouvrées, la musique d’attente, etc.
    
    <div>
    

    > [!NOTE]  
    > Lorsque vous voulez créer un flux de travail géré, vous devez créer le flux travail en tant que flux de travail actif. Après avoir enregistré un flux de travail géré et actif, vous pouvez le modifier et le désactiver.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

