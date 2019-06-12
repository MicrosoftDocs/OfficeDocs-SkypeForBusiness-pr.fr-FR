---
title: 'Lync Server 2013: configuration des stratégies de site pour l’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up site policies for Archiving
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48185613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08a4ccd7f88f21aaf0c7e3d1575b9e4a887c31d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a>Configuration de stratégies de site pour l’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-09_

Vous pouvez activer ou désactiver l’archivage pour des sites spécifiques en créant et en configurant une stratégie d’archivage pour chacun de ces sites. Une stratégie de site remplace la stratégie globale, mais les stratégies utilisateur remplacent les stratégies de site. Les stratégies d’archivage ne s’appliquent que si vous n’utilisez pas l’intégration de Microsoft Exchange ou, si vous utilisez l’intégration de Microsoft Exchange, mais que certains utilisateurs ne sont pas hébergés sur Exchange 2013 et disposent de leurs boîtes aux lettres pour la conservation inaltérable.

Pour plus d’informations sur le fonctionnement des stratégies d’archivage, y compris la hiérarchie pour les stratégies globales, de site et d’utilisateur, voir fonctionnement [de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, documentation de déploiement, ou documentation sur les opérations.

<div>


> [!NOTE]  
> Si vous activez l’intégration de Microsoft Exchange pour votre déploiement, les stratégies de conservation sur place permettent de contrôler si l’archivage est activé pour les utilisateurs hébergés sur Exchange 2013 et que leurs boîtes aux lettres sont placées sur place. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuration de stratégies d’archivage dans Lync server 2013 lors de l’utilisation d’une intégration Exchange Server</A> dans la documentation de déploiement.<BR>Vous devez spécifier toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage des communications internes ou externes dans les stratégies d’archivage. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-configuring-archiving-options.md">Configuration des options d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a>Pour créer une stratégie d’archivage pour un site

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server 2013.

3.  Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **stratégie**d’archivage.
    
    Pour plus d’informations sur le fonctionnement des stratégies d’archivage, y compris la hiérarchie pour les stratégies globales, de site et d’utilisateur, voir fonctionnement [de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, documentation de déploiement, ou documentation sur les opérations.

4.  Cliquez sur **Créer**, puis sur **Stratégie de site**.

5.  Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.

6.  Dans **Nouvelle stratégie d’archivage**, procédez comme suit :
    
      - Dans **Nom**, spécifiez le nom pour la stratégie de site.
    
      - Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, stratégie de site pour Redmond).
    
      - Pour contrôler l’archivage des communications internes pour le site spécifié, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
      - Pour contrôler l’archivage des communications externes pour le site spécifié, activez ou désactivez la case à cocher **Archiver les communications externes**.

7.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

