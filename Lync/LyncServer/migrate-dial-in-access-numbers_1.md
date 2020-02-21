---
title: Faire migrer les numéros d’accès entrant
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4efd83a0d874876bd00d9ebc880a7ae508db8605
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>Faire migrer les numéros d’accès entrant

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-26_

La migration des numéros d’accès entrants nécessite deux étapes : exécution de l’applet de commande **Import-applet cslegacyconfiguration** (terminée précédemment dans [importer des stratégies et des paramètres](import-policies-and-settings.md)) pour migrer les plans de numérotation et les autres paramètres de numéro d’accès entrant, et exécution de la cmdlet **Move-CsApplicationEndpoint** pour migrer les objets contact.

<div>

## <a name="to-migrate-dial-in-access-numbers"></a>Pour faire migrer les numéros d’accès entrant

1.  Ouvrez l’outil d’administration Office Communications Server 2007 R2.

2.  Dans l’arborescence de la console, cliquez avec le bouton droit sur le nœud Forêt, cliquez sur **Propriétés**, puis sur **Propriétés de Intendant Conférence**.

3.  Sous l’onglet **Numéros de téléphone d’accès**, cliquez sur **Traité par le pool** pour trier les numéros de téléphone d’accès par leur pool associé, et identifiez tous les numéros d’accès pour le pool à partir duquel vous effectuez la migration.

4.  Pour identifier l’URI SIP de chaque numéro d’accès, double-cliquez sur le numéro d’accès pour ouvrir la boîte de dialogue **Modifier le numéro de l’Intendant Conférence** et regardez sous **URI SIP**.

5.  Ouvrez Lync Server Management Shell.

6.  Pour déplacer chaque numéro d’accès entrant vers un pool hébergé sur Lync Server 2013, exécutez :
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  Dans l’outil d’administration Office Communications Server 2007 R2, sous l’onglet **numéros de téléphone d’accès** , vérifiez qu’aucun numéro d’accès entrant n’est conservé pour le pool Office Communications Server 2007 R2 à partir duquel vous effectuez la migration.

</div>

</div>

<span> </span>

</div>

</div>

</div>

