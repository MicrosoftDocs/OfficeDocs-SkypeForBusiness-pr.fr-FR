---
title: Créer ou modifier un ensemble de paramètres de configuration de Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b3eaf347693d079ef713716c5ebd0d8c470feef
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="75be6-102">Créer ou modifier un ensemble de paramètres de configuration de Lync Phone Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75be6-102">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75be6-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="75be6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="75be6-104">Lorsque vous installez Lync Server, vous obtenez une collection globale de paramètres Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="75be6-104">When you install Lync Server, you get a global collection of Lync Phone Edition settings.</span></span> <span data-ttu-id="75be6-105">Ces paramètres s’appliquent à tous les appareils exécutant Lync Phone Edition dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="75be6-105">These settings apply to all devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="75be6-106">Vous pouvez modifier ces paramètres à tout moment.</span><span class="sxs-lookup"><span data-stu-id="75be6-106">You can change these settings at any time.</span></span> <span data-ttu-id="75be6-107">Vous pouvez également définir une nouvelle collection de paramètres qui s’appliquent aux appareils d’un site spécifique.</span><span class="sxs-lookup"><span data-stu-id="75be6-107">You can also set up a new collection of settings that apply to the devices in a specific site.</span></span> <span data-ttu-id="75be6-108">Les paramètres de site sont prioritaires par rapport aux paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="75be6-108">Site settings take precedence over global settings.</span></span>

<span data-ttu-id="75be6-109">Les paramètres de configuration comprennent le nom de la collection, l’étendue (globale ou le site), le paramètre de sécurité SIP, le niveau de journalisation, le niveau de qualité de service (QoS), le paramètre de verrouillage du téléphone et les détails du verrouillage du téléphone, c’est-à-dire le nombre de fois qu’un numéro d’identification personnelle est déverrouillé ( Code confidentiel) doit comporter et b) le téléphone reste inactif avant de se bloquer.</span><span class="sxs-lookup"><span data-stu-id="75be6-109">Configuration settings consist of the collection name, scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, how long the a) unlock personal identification number (PIN) must be and b) phone stays idle before locking itself.</span></span>

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a><span data-ttu-id="75be6-110">Pour créer une collection de paramètres de configuration de Lync Phone Edition ou des paramètres d’édition pour une collection existante</span><span class="sxs-lookup"><span data-stu-id="75be6-110">To create a collection of Lync Phone Edition configuration settings or edit settings for an existing collection</span></span>

1.  <span data-ttu-id="75be6-111">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="75be6-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="75be6-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="75be6-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="75be6-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="75be6-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="75be6-114">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton navigation de **configuration d’appareil** .</span><span class="sxs-lookup"><span data-stu-id="75be6-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="75be6-115">Dans la page Configuration de l' **appareil** , effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="75be6-115">On the **Device Configuration** page, do one of the following:</span></span>
    
      - <span data-ttu-id="75be6-116">Pour créer une nouvelle collection de paramètres de configuration de Lync Phone Edition, cliquez sur **nouveau**, sélectionnez un site, cliquez sur **OK**, passez en revue les paramètres par défaut et, si vous le souhaitez, apportez les modifications souhaitées.</span><span class="sxs-lookup"><span data-stu-id="75be6-116">To create a new collection of Lync Phone Edition configuration settings, click **New**, select a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
      - <span data-ttu-id="75be6-117">Pour modifier l’un des paramètres d’une collection existante, cliquez dessus, cliquez sur le menu **édition** , cliquez sur **afficher les détails**, puis apportez les modifications souhaitées.</span><span class="sxs-lookup"><span data-stu-id="75be6-117">To edit any of the settings in an existing collection, click the collection, click the **Edit** menu, click **Show details**, and then make your changes.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="75be6-118">Pour revenir à l’utilisation des paramètres par défaut pour la collection globale, cliquez sur la collection globale, cliquez sur le menu <STRONG>Edition</STRONG> , cliquez sur <STRONG>supprimer</STRONG>, puis cliquez sur <STRONG>OK</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="75be6-118">To go back to using the default settings for the global collection, click the global collection, click the <STRONG>Edit</STRONG> menu, click <STRONG>Delete</STRONG>, and then click <STRONG>OK</STRONG>.</span></span> <span data-ttu-id="75be6-119">Cette opération n’entraîne pas la suppression de la collection globale. elle réinitialise uniquement les paramètres aux valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="75be6-119">This will not delete the global collection; it just resets the settings to the defaults.</span></span>

        
        </div>

5.  <span data-ttu-id="75be6-120">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="75be6-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="75be6-121">Création de nouveaux paramètres de configuration de Lync Phone Edition à l’aide d’applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="75be6-121">Creating New Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="75be6-122">Vous pouvez créer des paramètres de configuration de Lync Phone Edition (à l’étendue du site uniquement) à l’aide de Windows PowerShell et de l’applet **de nouvelle cmdlet New-CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="75be6-122">You can create Lync Phone Edition configuration settings can (at the site scope only) by using Windows PowerShell and the **New-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="75be6-123">Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75be6-123">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="75be6-124">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="75be6-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="75be6-125">Pour créer des paramètres de configuration de Lync Phone Edition utilisant les valeurs par défaut</span><span class="sxs-lookup"><span data-stu-id="75be6-125">To create new Lync Phone Edition configuration settings that use the default values</span></span>

  - <span data-ttu-id="75be6-126">Cette commande crée un ensemble de paramètres de configuration de téléphone de UC pour le site de Redmond :</span><span class="sxs-lookup"><span data-stu-id="75be6-126">This command creates a new set of UC phone configuration settings for the Redmond site:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="75be6-127">Comme aucun paramètre (autre que celui obligatoire sur l’identité) n’a été précisé dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="75be6-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="75be6-128">Pour modifier une valeur de propriété unique lors de la création de nouveaux paramètres de configuration de Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="75be6-128">To change a single property value when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="75be6-129">Pour créer des paramètres qui font appel à d’autres valeurs de propriétés, incluez simplement le paramètre approprié et sa valeur.</span><span class="sxs-lookup"><span data-stu-id="75be6-129">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="75be6-130">Par exemple, pour créer un ensemble de paramètres de configuration de téléphone de type UC qui, par défaut, nécessite le verrouillage du téléphone, utilisez une commande comme celle-ci :</span><span class="sxs-lookup"><span data-stu-id="75be6-130">For example, to create a collection of UC phone configuration settings that, by default, require phone locking, use a command like this:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="75be6-131">Pour modifier plusieurs valeurs de propriétés lors de la création de nouveaux paramètres de configuration de Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="75be6-131">To change multiple property values when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="75be6-132">Vous pouvez modifier plusieurs valeurs de propriétés en incluant plusieurs paramètres.</span><span class="sxs-lookup"><span data-stu-id="75be6-132">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="75be6-133">Par exemple, cette commande applique le verrouillage du téléphone et définit la longueur minimale du code confidentiel sur 8 chiffres :</span><span class="sxs-lookup"><span data-stu-id="75be6-133">For example, this command enforces phone locking and also sets the minimum PIN length to 8 digits:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

<span data-ttu-id="75be6-134">Pour plus d’informations, consultez la rubrique [New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15)).</span><span class="sxs-lookup"><span data-stu-id="75be6-134">For details, see [New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15)).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="75be6-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="75be6-135">See Also</span></span>


[<span data-ttu-id="75be6-136">Supprimer une collection existante de paramètres de configuration de Lync Phone Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75be6-136">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="75be6-137">Configurer les paramètres de sécurité de Lync Phone Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75be6-137">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="75be6-138">Renforcer le verrouillage du téléphone dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75be6-138">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

