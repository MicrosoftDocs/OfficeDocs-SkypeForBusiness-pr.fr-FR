---
title: Migrer les numéros d’accès entrant
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b86db6e669fd5f52827591c25e5bb237bd9ee012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>Migrer les numéros d’accès entrant

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-26_

La migration des numéros d’accès rendez-vous implique deux étapes: l’exécution de l’applet de connexion **Import-CsLegacyConfiguration** (exécutée précédemment dans l' [importation des stratégies et des paramètres](import-policies-and-settings.md)) pour migrer les **plans de numérotation et autres paramètres de numéro d’accès Applet de passe Move-CsApplicationEndpoint** pour migrer les objets de contact.

<div>

## <a name="to-migrate-dial-in-access-numbers"></a>Pour migrer des numéros d’accès entrants

1.  Ouvrez l’outil d’administration d’Office Communications Server 2007 R2.

2.  Dans l’arborescence de la console, cliquez avec le bouton droit sur le nœud de la forêt, cliquez sur **Propriétés**, puis sur **Propriétés du surveillant de conférence**.

3.  Dans l’onglet **numéros de téléphone d’accès** , cliquez sur **desservi par le pool** pour trier les numéros de téléphone d’accès par leur liste de connexions associées, puis identifiez tous les numéros d’accès pour le pool à partir duquel vous effectuez la migration.

4.  Pour identifier l’URI SIP de chaque numéro d’accès, double-cliquez sur le numéro d’accès pour ouvrir la boîte de dialogue **modifier le numéro du surveillant de conférences** et recherchez sous **URI SIP**.

5.  Ouvrez Lync Server Management Shell.

6.  Pour déplacer chaque numéro d’accès entrant vers un pool hébergé sur Lync Server 2013, exécutez:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  Dans l’onglet **numéros de téléphone d’accès** de l’outil d’administration d’Office communications Server 2007 R2, vérifiez qu’aucun numéro d’accès entrant ne reste pour le pool Office communications Server 2007 R2 à partir duquel vous effectuez la migration.

</div>

</div>

<span> </span>

</div>

</div>

</div>

