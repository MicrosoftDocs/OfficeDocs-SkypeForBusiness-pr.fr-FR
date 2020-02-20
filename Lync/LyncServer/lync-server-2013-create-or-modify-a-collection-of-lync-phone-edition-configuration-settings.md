---
title: Création ou modification d’une collection de paramètres de configuration de Lync Phone Edition
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
ms.openlocfilehash: 359c08c0ce8be63019856f05988ee30cd4419bf7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="17413-102">Création ou modification d’une collection de paramètres de configuration Lync Phone Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17413-102">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17413-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="17413-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="17413-104">Lorsque vous installez Lync Server, vous obtenez une collection globale de paramètres Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="17413-104">When you install Lync Server, you get a global collection of Lync Phone Edition settings.</span></span> <span data-ttu-id="17413-105">Ces paramètres s’appliquent à tous les appareils exécutant Lync Phone Edition dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="17413-105">These settings apply to all devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="17413-106">Vous pouvez modifier ces paramètres à tout moment.</span><span class="sxs-lookup"><span data-stu-id="17413-106">You can change these settings at any time.</span></span> <span data-ttu-id="17413-107">Vous pouvez également configurer une nouvelle collection de paramètres qui s’applique aux appareils d’un site spécifique.</span><span class="sxs-lookup"><span data-stu-id="17413-107">You can also set up a new collection of settings that apply to the devices in a specific site.</span></span> <span data-ttu-id="17413-108">Les paramètres du site prévalent sur les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="17413-108">Site settings take precedence over global settings.</span></span>

<span data-ttu-id="17413-109">Les paramètres de configuration comprennent le nom de la collection, l’étendue (globale ou site), le paramètre de sécurité SIP, le niveau de journalisation, le niveau de qualité de service de la voix (QoS), le paramètre de verrouillage du téléphone et les détails du verrouillage du téléphone, c’est-à-dire a) la longueur requise du code confidentiel de déverrouillage et b) le délai d’inactivité du téléphone avant son propre verrouillage.</span><span class="sxs-lookup"><span data-stu-id="17413-109">Configuration settings consist of the collection name, scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, how long the a) unlock personal identification number (PIN) must be and b) phone stays idle before locking itself.</span></span>

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a><span data-ttu-id="17413-110">Pour créer une collection de paramètres de configuration de Lync Phone Edition ou modifier les paramètres d’une collection existante</span><span class="sxs-lookup"><span data-stu-id="17413-110">To create a collection of Lync Phone Edition configuration settings or edit settings for an existing collection</span></span>

1.  <span data-ttu-id="17413-111">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="17413-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="17413-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="17413-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="17413-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="17413-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="17413-114">Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Configuration du périphérique**.</span><span class="sxs-lookup"><span data-stu-id="17413-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="17413-115">Dans la page **Configuration du périphérique**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="17413-115">On the **Device Configuration** page, do one of the following:</span></span>
    
      - <span data-ttu-id="17413-116">Pour créer une nouvelle collection de paramètres de configuration de Lync Phone Edition, cliquez sur **nouveau**, sélectionnez un site, cliquez sur **OK**, vérifiez les paramètres par défaut et, si vous le souhaitez, effectuez les modifications nécessaires.</span><span class="sxs-lookup"><span data-stu-id="17413-116">To create a new collection of Lync Phone Edition configuration settings, click **New**, select a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
      - <span data-ttu-id="17413-117">Pour modifier l’un des paramètres d’une collection existante, cliquez sur la collection, cliquez sur le menu **Modifier**, cliquez sur **Afficher les détails**, puis apportez vos modifications.</span><span class="sxs-lookup"><span data-stu-id="17413-117">To edit any of the settings in an existing collection, click the collection, click the **Edit** menu, click **Show details**, and then make your changes.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="17413-p103">Pour revenir à l’utilisation des paramètres par défaut de la collection globale, cliquez sur la collection globale, cliquez sur le menu <STRONG>Modifier</STRONG>, cliquez sur <STRONG>Supprimer</STRONG>, puis sur <STRONG>OK</STRONG>. Cela ne supprime pas la collection globale, mais rétablit simplement les paramètres à leurs valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="17413-p103">To go back to using the default settings for the global collection, click the global collection, click the <STRONG>Edit</STRONG> menu, click <STRONG>Delete</STRONG>, and then click <STRONG>OK</STRONG>. This will not delete the global collection; it just resets the settings to the defaults.</span></span>

        
        </div>

5.  <span data-ttu-id="17413-120">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="17413-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="17413-121">Création de nouveaux paramètres de configuration de Lync Phone Edition à l’aide d’applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="17413-121">Creating New Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="17413-122">Vous pouvez créer des paramètres de configuration de Lync Phone Edition (au niveau de l’étendue site uniquement) à l’aide de Windows PowerShell et de la cmdlet **New-CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="17413-122">You can create Lync Phone Edition configuration settings can (at the site scope only) by using Windows PowerShell and the **New-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="17413-123">Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17413-123">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="17413-124">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="17413-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="17413-125">Pour créer de nouveaux paramètres de configuration de Lync Phone Edition qui utilisent les valeurs par défaut</span><span class="sxs-lookup"><span data-stu-id="17413-125">To create new Lync Phone Edition configuration settings that use the default values</span></span>

  - <span data-ttu-id="17413-126">Cette commande permet de créer un jeu de paramètres de configuration de téléphonie UC pour le site Redmond :</span><span class="sxs-lookup"><span data-stu-id="17413-126">This command creates a new set of UC phone configuration settings for the Redmond site:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="17413-127">Étant donné qu’aucun paramètre (autre que le paramètre Identity obligatoire) n’a été spécifié dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="17413-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="17413-128">Pour modifier une seule valeur de propriété lors de la création de nouveaux paramètres de configuration de Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="17413-128">To change a single property value when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="17413-p105">Pour créer des paramètres qui utilisent des valeurs de propriété différentes, il suffit d’inclure le paramètre et la valeur de paramètre appropriés. Par exemple, pour créer une collection de paramètres de configuration de téléphonie UC qui, par défaut, exige le verrouillage du téléphone, utilisez une commande comme celle-ci :</span><span class="sxs-lookup"><span data-stu-id="17413-p105">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of UC phone configuration settings that, by default, require phone locking, use a command like this:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="17413-131">Pour modifier plusieurs valeurs de propriété lors de la création de nouveaux paramètres de configuration de Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="17413-131">To change multiple property values when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="17413-p106">Il est possible de modifier plusieurs valeurs de propriété en incluant plusieurs paramètres. Par exemple, cette commande permet de mettre en application le verrouillage du téléphone et également de définir une longueur minimale de 8 chiffres pour le code confidentiel :</span><span class="sxs-lookup"><span data-stu-id="17413-p106">Multiple property values can be modified by including multiple parameters. For example, this command enforces phone locking and also sets the minimum PIN length to 8 digits:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

<span data-ttu-id="17413-134">Pour plus d’informations, consultez la rubrique [New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15)).</span><span class="sxs-lookup"><span data-stu-id="17413-134">For details, see [New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15)).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="17413-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="17413-135">See Also</span></span>


[<span data-ttu-id="17413-136">Supprimer une collection existante de paramètres de configuration Lync Phone Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17413-136">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="17413-137">Configurer les paramètres de sécurité pour Lync Phone Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17413-137">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="17413-138">Appliquer le verrouillage du téléphone dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17413-138">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

