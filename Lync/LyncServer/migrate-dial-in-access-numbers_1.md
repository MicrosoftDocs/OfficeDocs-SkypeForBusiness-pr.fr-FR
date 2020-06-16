---
title: Faire migrer les numéros d’accès entrant
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6654c084be4915d48c4148c90b3888295c887f08
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="6c4b4-102">Faire migrer les numéros d’accès entrant</span><span class="sxs-lookup"><span data-stu-id="6c4b4-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c4b4-103">_**Dernière modification de la rubrique :** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="6c4b4-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="6c4b4-104">La migration des numéros d’accès entrants nécessite deux étapes : exécution de l’applet de commande **Import-applet cslegacyconfiguration** (terminée précédemment dans [importer des stratégies et des paramètres](import-policies-and-settings.md)) pour migrer les plans de numérotation et les autres paramètres de numéro d’accès entrant, et exécution de la cmdlet **Move-CsApplicationEndpoint** pour migrer les objets contact.</span><span class="sxs-lookup"><span data-stu-id="6c4b4-104">Migrating dial-in access numbers requires two steps: running the **Import-CsLegacyConfiguration** cmdlet (completed earlier in [Import policies and settings](import-policies-and-settings.md)) to migrate dial plans and other dial-in access number settings, and running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span>

<div>

## <a name="to-migrate-dial-in-access-numbers"></a><span data-ttu-id="6c4b4-105">Pour faire migrer les numéros d’accès entrant</span><span class="sxs-lookup"><span data-stu-id="6c4b4-105">To migrate dial-in access numbers</span></span>

1.  <span data-ttu-id="6c4b4-106">Ouvrez l’outil d’administration Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6c4b4-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="6c4b4-107">Dans l’arborescence de la console, cliquez avec le bouton droit sur le nœud Forêt, cliquez sur **Propriétés**, puis sur **Propriétés de Intendant Conférence**.</span><span class="sxs-lookup"><span data-stu-id="6c4b4-107">In the console tree, right-click the forest node, click **Properties**, and then click **Conferencing Attendant Properties**.</span></span>

3.  <span data-ttu-id="6c4b4-108">Sous l’onglet **Numéros de téléphone d’accès**, cliquez sur **Traité par le pool** pour trier les numéros de téléphone d’accès par leur pool associé, et identifiez tous les numéros d’accès pour le pool à partir duquel vous effectuez la migration.</span><span class="sxs-lookup"><span data-stu-id="6c4b4-108">On the **Access Phone Numbers** tab, click **Serviced by Pool** to sort the access phone numbers by their associated pool, and identify all the access numbers for the pool from which you are migrating.</span></span>

4.  <span data-ttu-id="6c4b4-109">Pour identifier l’URI SIP de chaque numéro d’accès, double-cliquez sur le numéro d’accès pour ouvrir la boîte de dialogue **Modifier le numéro de l’Intendant Conférence** et regardez sous **URI SIP**.</span><span class="sxs-lookup"><span data-stu-id="6c4b4-109">To identify the SIP URI for each access number, double-click the access number to open the **Edit Conferencing Attendant Number** dialog box, and look under **SIP URI**.</span></span>

5.  <span data-ttu-id="6c4b4-110">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6c4b4-110">Open the Lync Server Management Shell.</span></span>

6.  <span data-ttu-id="6c4b4-111">Pour déplacer chaque numéro d’accès entrant vers un pool hébergé sur Lync Server 2013, exécutez :</span><span class="sxs-lookup"><span data-stu-id="6c4b4-111">To move each dial-in access number to a pool hosted on Lync Server 2013, run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  <span data-ttu-id="6c4b4-112">Dans l’outil d’administration Office Communications Server 2007 R2, sous l’onglet **numéros de téléphone d’accès** , vérifiez qu’aucun numéro d’accès entrant n’est conservé pour le pool Office Communications Server 2007 R2 à partir duquel vous effectuez la migration.</span><span class="sxs-lookup"><span data-stu-id="6c4b4-112">In the Office Communications Server 2007 R2 Administrative tool, on the **Access Phone Numbers** tab, verify that no dial-in access numbers remain for the Office Communications Server 2007 R2 pool from which you are migrating.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

