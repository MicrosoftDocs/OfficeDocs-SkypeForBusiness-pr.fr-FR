---
title: Configurer le client Skype entreprise dans Lync Server 2013
description: Configurez le client Skype entreprise dans Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7f75ae0fa61d9048991934a0ecce7a886079961
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542970"
---
# <a name="configure-the-client-experience-with-skype-for-business"></a><span data-ttu-id="12146-103">Configuration de l’expérience client avec Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="12146-103">Configure the client experience with Skype for Business</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12146-104">_**Dernière modification de la rubrique :** 2015-09-17_</span><span class="sxs-lookup"><span data-stu-id="12146-104">_**Topic Last Modified:** 2015-09-17_</span></span>

<span data-ttu-id="12146-105">**Résumé :** Cette rubrique décrit comment configurer l’expérience client pour les utilisateurs de clients Skype entreprise dans un environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12146-105">**Summary:** This topic describes how to configure the client experience for Skype for Business client users in a Lync Server 2013 environment.</span></span> <span data-ttu-id="12146-106">Vous pouvez configurer l’expérience client uniquement si vous exécutez Lync Server 2013 avec la mise à jour cumulative de décembre 2014 (5.0.8308.857) ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="12146-106">You can configure the client experience only if you are running Lync Server 2013 with the December 2014 Cumulative Update (5.0.8308.857) or later installed.</span></span> <span data-ttu-id="12146-107">Pour plus d’informations sur la mise à jour de Lync Server 2013, voir [mises à jour pour Lync server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).</span><span class="sxs-lookup"><span data-stu-id="12146-107">For information about updating Lync Server 2013, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).</span></span>

<span data-ttu-id="12146-108">Skype entreprise offre une nouvelle expérience utilisateur basée sur l’expérience de produit client Skype.</span><span class="sxs-lookup"><span data-stu-id="12146-108">Skype for Business provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="12146-109">En plus de toutes les fonctionnalités de Lync, Skype entreprise offre de nouvelles fonctionnalités avec des contrôles simplifiés et des icônes familières.</span><span class="sxs-lookup"><span data-stu-id="12146-109">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="12146-110">Pour plus d’informations sur la nouvelle expérience client, voir [Lync est maintenant Skype entreprise--voir what’s New](https://go.microsoft.com/fwlink/?linkid=529022).</span><span class="sxs-lookup"><span data-stu-id="12146-110">For detailed information about the new client experience, see [Lync is now Skype for Business -- see what's new](https://go.microsoft.com/fwlink/?linkid=529022).</span></span>

<span data-ttu-id="12146-111">Lync Server 2013 prend en charge la nouvelle expérience client Skype entreprise, ainsi que l’expérience client Lync.</span><span class="sxs-lookup"><span data-stu-id="12146-111">Lync Server 2013 supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="12146-112">En tant qu’administrateur, vous pouvez choisir l’expérience client préférée pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="12146-112">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="12146-113">Par exemple, vous pouvez déployer l’expérience client Lync jusqu’à ce que les utilisateurs de votre organisation soient entièrement formés à la nouvelle expérience Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="12146-113">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="12146-114">Si vous n’avez pas encore mis à niveau tous les utilisateurs vers Skype entreprise Server 2015, vous souhaiterez peut-être que tous les utilisateurs bénéficient de la même expérience client jusqu’à ce que tous soient mis à niveau vers le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="12146-114">Or, if you have not yet upgraded all users to Skype for Business Server 2015, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="12146-115">Si votre organisation a à la fois Skype entreprise Server 2015 et Lync Server 2013 déployés, l’expérience client par défaut varie en fonction des versions du serveur et des paramètres de l’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="12146-115">If your organization has both Skype for Business Server 2015 and Lync Server 2013 deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="12146-116">Lorsque les utilisateurs lancent Skype entreprise pour la première fois, ils voient toujours l’interface utilisateur de Skype entreprise, même si vous avez sélectionné l’interface utilisateur Lync.</span><span class="sxs-lookup"><span data-stu-id="12146-116">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync user interface.</span></span> <span data-ttu-id="12146-117">Après quelques minutes, les utilisateurs sont invités à passer en mode Lync.</span><span class="sxs-lookup"><span data-stu-id="12146-117">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="12146-118">Pour plus d’informations, voir <STRONG>First Launch client Behavior</STRONG> plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="12146-118">For more information, see <STRONG>First launch client behavior</STRONG> later in this topic.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="12146-119">L’expérience client Lync 2013 n’est pas une option pour les versions clientes de Skype entreprise 2016.</span><span class="sxs-lookup"><span data-stu-id="12146-119">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="12146-120">Avant de configurer votre environnement client pour qu’il utilise le client Lync 2013, vérifiez la version du client pour vous assurer qu’elle ne commence pas par le numéro 16 ; par exemple : 16. x.x.x.</span><span class="sxs-lookup"><span data-stu-id="12146-120">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span>



</div>

<div>

## <a name="configure-the-client-experience"></a><span data-ttu-id="12146-121">Configurer l’expérience client</span><span class="sxs-lookup"><span data-stu-id="12146-121">Configure the client experience</span></span>

<span data-ttu-id="12146-122">Vous pouvez spécifier l’expérience client que les utilisateurs de votre organisation verront à l’aide de la cmdlet **Set-CSClientPolicy** avec le paramètre EnableSkypeUI.</span><span class="sxs-lookup"><span data-stu-id="12146-122">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter.</span></span> <span data-ttu-id="12146-123">La commande suivante sélectionne l’expérience client Skype entreprise pour tous les utilisateurs de votre organisation concernés par la stratégie globale (Rappelez-vous que les stratégies de site ou spécifiques à l’utilisateur remplacent la stratégie globale) :</span><span class="sxs-lookup"><span data-stu-id="12146-123">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

<span data-ttu-id="12146-124">La commande suivante sélectionne l’expérience client Lync pour tous les utilisateurs de votre organisation concernés par la stratégie globale :</span><span class="sxs-lookup"><span data-stu-id="12146-124">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

<span data-ttu-id="12146-125">La commande suivante sélectionne l’expérience client Skype entreprise pour tous les utilisateurs au sein du site de Redmond :</span><span class="sxs-lookup"><span data-stu-id="12146-125">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

<span data-ttu-id="12146-126">Si vous souhaitez configurer l’expérience client pour des utilisateurs spécifiques au sein de votre organisation, vous pouvez créer une nouvelle stratégie utilisateur à l’aide de la cmdlet **New-CsClientPolicy** , puis affecter la stratégie à des utilisateurs spécifiques à l’aide de la cmdlet **Grant-CsClientPolicy** .</span><span class="sxs-lookup"><span data-stu-id="12146-126">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>

<span data-ttu-id="12146-127">Par exemple, la commande suivante crée une nouvelle stratégie client, SalesClientUI, qui sélectionne l’expérience client Skype entreprise :</span><span class="sxs-lookup"><span data-stu-id="12146-127">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

<span data-ttu-id="12146-128">La commande suivante affecte la stratégie, SalesClientUI, à tous les membres du service des ventes :</span><span class="sxs-lookup"><span data-stu-id="12146-128">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="12146-129">Comportements de client de premier lancement</span><span class="sxs-lookup"><span data-stu-id="12146-129">First launch client behaviors</span></span>

<span data-ttu-id="12146-130">Par défaut, lorsque les utilisateurs lancent Skype entreprise pour la première fois, ils voient toujours l’interface utilisateur de Skype entreprise, même si vous avez sélectionné l’expérience client Lync en définissant la valeur du paramètre EnableSkypeUI sur $False comme décrit précédemment.</span><span class="sxs-lookup"><span data-stu-id="12146-130">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="12146-131">Après quelques minutes, les utilisateurs sont invités à passer en mode Lync.</span><span class="sxs-lookup"><span data-stu-id="12146-131">After several minutes, users will then be asked to switch to Lync mode.</span></span>

<span data-ttu-id="12146-132">Si vous souhaitez afficher l’interface utilisateur Lync lorsque les utilisateurs lancent le client Skype entreprise pour la première fois, suivez ces étapes avant le démarrage du client pour la première fois après sa mise à jour :</span><span class="sxs-lookup"><span data-stu-id="12146-132">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>

1.  <span data-ttu-id="12146-133">Vérifiez que la valeur de `EnableSkypeUI` est définie sur $false dans la stratégie que vous utilisez comme décrit précédemment.</span><span class="sxs-lookup"><span data-stu-id="12146-133">Confirm that the value of `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>

2.  <span data-ttu-id="12146-134">Mettez à jour le registre système sur l’ordinateur de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="12146-134">Update the system registry on the user's computer.</span></span> <span data-ttu-id="12146-135">Vous devez effectuer cette opération avant la première exécution du client Skype entreprise, et vous ne devez effectuer cette opération qu’une seule fois.</span><span class="sxs-lookup"><span data-stu-id="12146-135">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="12146-136">Pour plus d’informations sur la création d’un objet de stratégie de groupe pour mettre à jour le registre sur un ordinateur joint à un domaine, voir la section plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="12146-136">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="12146-137">Dans la clé \*\* \[ HKEY \_ Current \_ User \\ Software \\ Microsoft \\ Office \\ \] Lync\*\* , créez une valeur **binaire** .</span><span class="sxs-lookup"><span data-stu-id="12146-137">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="12146-138">Le **nom** de la valeur doit être **EnableSkypeUI**et les **données de valeur** doivent être définies sur **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="12146-138">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="12146-139">La clé doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="12146-139">The key should look like the following:</span></span>
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

<span data-ttu-id="12146-140">L’interface utilisateur de Lync apparaît maintenant lorsque les utilisateurs lancent le client Skype entreprise pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="12146-140">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="12146-141">Contrôler l’affichage du didacticiel de l’écran d’accueil</span><span class="sxs-lookup"><span data-stu-id="12146-141">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="12146-142">Lorsque les utilisateurs ouvrent le client Skype entreprise, le comportement par défaut consiste à afficher un écran d’accueil qui inclut *7 conseils rapides que la plupart des personnes demandent*.</span><span class="sxs-lookup"><span data-stu-id="12146-142">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="12146-143">Vous pouvez désactiver l’affichage de l’écran d’accueil tout en autorisant les utilisateurs à accéder au didacticiel en ajoutant la valeur de Registre suivante sur l’ordinateur client :</span><span class="sxs-lookup"><span data-stu-id="12146-143">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>

<span data-ttu-id="12146-144">Dans la clé \*\* \[ \_ \_ \\ \\ Microsoft \\ Office \\ 15,0 \\ Lync \] Software User Software\*\* , créez une nouvelle **valeur DWORD (32 bits)**.</span><span class="sxs-lookup"><span data-stu-id="12146-144">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="12146-145">Le **nom** de la valeur doit être **IsBasicTutorialSeenByUser**et les **données de valeur** doivent être définies sur **1**.</span><span class="sxs-lookup"><span data-stu-id="12146-145">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>

<span data-ttu-id="12146-146">La clé doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="12146-146">The key should look like the following:</span></span>

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="12146-147">Désactivation du didacticiel client</span><span class="sxs-lookup"><span data-stu-id="12146-147">Turn off the client tutorial</span></span>

<span data-ttu-id="12146-148">Si vous ne souhaitez pas que vos utilisateurs puissent accéder au didacticiel, vous pouvez désactiver le didacticiel client avec la valeur de Registre suivante :</span><span class="sxs-lookup"><span data-stu-id="12146-148">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>

<span data-ttu-id="12146-149">Dans la clé \*\* \[ \_ \_ \\ \\ Microsoft \\ Office \\ 15,0 \\ Lync \] Software User Software\*\* , créez une nouvelle **valeur DWORD (32 bits)**.</span><span class="sxs-lookup"><span data-stu-id="12146-149">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="12146-150">Le **nom** de la valeur doit être **TutorialFeatureEnabled**et les **données de valeur** doivent être définies sur **0**.</span><span class="sxs-lookup"><span data-stu-id="12146-150">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>

    "TutorialFeatureEnabled"=dword:00000000

<span data-ttu-id="12146-151">Vous pouvez réactiver le didacticiel en définissant la **valeur** sur **1**.</span><span class="sxs-lookup"><span data-stu-id="12146-151">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>

</div>

</div>

<div>

## <a name="default-client-experiences"></a><span data-ttu-id="12146-152">Expériences client par défaut</span><span class="sxs-lookup"><span data-stu-id="12146-152">Default client experiences</span></span>

<span data-ttu-id="12146-153">Si votre organisation a à la fois Skype entreprise Server 2015 et Lync Server déployés, l’expérience client varie en fonction des versions de serveur et du paramètre de l’interface utilisateur Skype.</span><span class="sxs-lookup"><span data-stu-id="12146-153">If your organization has both Skype for Business Server 2015 and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="12146-154">Le tableau suivant indique l’expérience client initiale en fonction de la version du serveur et du paramètre de l’interface utilisateur :</span><span class="sxs-lookup"><span data-stu-id="12146-154">The following table shows the initial client experience based on server version and the UI setting:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="12146-155">Version du serveur</span><span class="sxs-lookup"><span data-stu-id="12146-155">Server version</span></span></p></th>
<th><p><span data-ttu-id="12146-156">Paramètre EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="12146-156">EnableSkypeUI setting</span></span></p></th>
<th><p><span data-ttu-id="12146-157">Expérience client</span><span class="sxs-lookup"><span data-stu-id="12146-157">Client experience</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12146-158">Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="12146-158">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="12146-159">Par défaut</span><span class="sxs-lookup"><span data-stu-id="12146-159">Default</span></span></p></td>
<td><p><span data-ttu-id="12146-160">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="12146-160">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12146-161">Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="12146-161">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="12146-162">Vrai</span><span class="sxs-lookup"><span data-stu-id="12146-162">True</span></span></p></td>
<td><p><span data-ttu-id="12146-163">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="12146-163">Skype for Business</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12146-164">Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="12146-164">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="12146-165">False</span><span class="sxs-lookup"><span data-stu-id="12146-165">False</span></span></p></td>
<td><p><span data-ttu-id="12146-166">L’utilisateur a demandé à passer en mode Lync (l’utilisateur peut passer à Skype entreprise ultérieurement si vous modifiez le paramètre de l’interface utilisateur pour $true)</span><span class="sxs-lookup"><span data-stu-id="12146-166">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12146-167">Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)</span><span class="sxs-lookup"><span data-stu-id="12146-167">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="12146-168">Par défaut</span><span class="sxs-lookup"><span data-stu-id="12146-168">Default</span></span></p></td>
<td><p><span data-ttu-id="12146-169">L’utilisateur a demandé à passer en mode Lync (l’utilisateur peut passer à Skype entreprise ultérieurement si vous modifiez le paramètre de l’interface utilisateur pour $true)</span><span class="sxs-lookup"><span data-stu-id="12146-169">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12146-170">Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)</span><span class="sxs-lookup"><span data-stu-id="12146-170">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="12146-171">Vrai</span><span class="sxs-lookup"><span data-stu-id="12146-171">True</span></span></p></td>
<td><p><span data-ttu-id="12146-172">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="12146-172">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12146-173">Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)</span><span class="sxs-lookup"><span data-stu-id="12146-173">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="12146-174">False</span><span class="sxs-lookup"><span data-stu-id="12146-174">False</span></span></p></td>
<td><p><span data-ttu-id="12146-175">L’utilisateur a demandé à passer en mode Lync (l’utilisateur peut passer à Skype entreprise ultérieurement si vous modifiez le paramètre de l’interface utilisateur pour $true)</span><span class="sxs-lookup"><span data-stu-id="12146-175">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12146-176">Lync Server 2010 ou Lync Server 2013 (sans correctifs)</span><span class="sxs-lookup"><span data-stu-id="12146-176">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="12146-177">Par défaut</span><span class="sxs-lookup"><span data-stu-id="12146-177">Default</span></span></p></td>
<td><p><span data-ttu-id="12146-178">L’utilisateur a demandé à passer à l’expérience client Lync (l’utilisateur ne peut pas passer à Skype entreprise plus tard)</span><span class="sxs-lookup"><span data-stu-id="12146-178">User asked to switch to Lync client experience (user cannot switch to Skype for Business later)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="12146-179">Le tableau suivant indique l’expérience client lorsque l’administrateur modifie le paramètre initial de l’expérience utilisateur Skype :</span><span class="sxs-lookup"><span data-stu-id="12146-179">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="12146-180">Version du serveur</span><span class="sxs-lookup"><span data-stu-id="12146-180">Server version</span></span></p></th>
<th><p><span data-ttu-id="12146-181">Paramètre de l’interface utilisateur Skype</span><span class="sxs-lookup"><span data-stu-id="12146-181">Skype UI setting</span></span></p></th>
<th><p><span data-ttu-id="12146-182">Interface utilisateur du client = Lync</span><span class="sxs-lookup"><span data-stu-id="12146-182">Client UI = Lync</span></span></p></th>
<th><p><span data-ttu-id="12146-183">Interface utilisateur du client = Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="12146-183">Client UI = Skype for Business</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12146-184">Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="12146-184">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="12146-185">Vrai</span><span class="sxs-lookup"><span data-stu-id="12146-185">True</span></span></p></td>
<td><p><span data-ttu-id="12146-186">Utilisateur invité à passer à Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="12146-186">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="12146-187">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="12146-187">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12146-188">Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="12146-188">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="12146-189">False</span><span class="sxs-lookup"><span data-stu-id="12146-189">False</span></span></p></td>
<td><p><span data-ttu-id="12146-190">Interface utilisateur Lync</span><span class="sxs-lookup"><span data-stu-id="12146-190">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="12146-191">Utilisateur invité à basculer vers l’interface utilisateur Lync</span><span class="sxs-lookup"><span data-stu-id="12146-191">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12146-192">Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)</span><span class="sxs-lookup"><span data-stu-id="12146-192">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="12146-193">Vrai</span><span class="sxs-lookup"><span data-stu-id="12146-193">True</span></span></p></td>
<td><p><span data-ttu-id="12146-194">Utilisateur invité à passer à Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="12146-194">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="12146-195">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="12146-195">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12146-196">Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)</span><span class="sxs-lookup"><span data-stu-id="12146-196">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="12146-197">False</span><span class="sxs-lookup"><span data-stu-id="12146-197">False</span></span></p></td>
<td><p><span data-ttu-id="12146-198">Interface utilisateur Lync</span><span class="sxs-lookup"><span data-stu-id="12146-198">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="12146-199">Utilisateur invité à basculer vers l’interface utilisateur Lync</span><span class="sxs-lookup"><span data-stu-id="12146-199">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12146-200">Lync Server 2010 ou Lync Server 2013 (sans correctifs)</span><span class="sxs-lookup"><span data-stu-id="12146-200">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="12146-201">Par défaut</span><span class="sxs-lookup"><span data-stu-id="12146-201">Default</span></span></p></td>
<td><p><span data-ttu-id="12146-202">Mode Lync (impossible de basculer vers Skype entreprise)</span><span class="sxs-lookup"><span data-stu-id="12146-202">Lync mode (cannot switch to Skype for Business)</span></span></p></td>
<td><p><span data-ttu-id="12146-203">Interface utilisateur Lync (impossible de basculer vers Skype entreprise)</span><span class="sxs-lookup"><span data-stu-id="12146-203">Lync UI (cannot switch to Skype for Business)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="12146-204">Les versions des correctifs nécessaires à la gestion de la configuration du client Skype entreprise sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="12146-204">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>

  - <span data-ttu-id="12146-205">Lync Server 2010-mise à jour cumulative de février 2015 (4.0.7577.710) pour Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="12146-205">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="12146-206">Pour plus d’informations, consultez la rubrique [mises à jour pour Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)</span><span class="sxs-lookup"><span data-stu-id="12146-206">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)</span></span>

  - <span data-ttu-id="12146-207">Lync Server 2013-mise à jour cumulative 2014 de décembre (5.0.8308.857) pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12146-207">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="12146-208">Pour plus d’informations, consultez la rubrique [mises à jour pour Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).</span><span class="sxs-lookup"><span data-stu-id="12146-208">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).</span></span>

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="12146-209">Créer un objet de stratégie de groupe pour modifier le registre sur un ordinateur joint à un domaine</span><span class="sxs-lookup"><span data-stu-id="12146-209">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="12146-210">La mise à jour du Registre pour afficher l’expérience client Lync la première fois qu’un utilisateur lance le client Skype entreprise, ne doit être exécutée qu’une seule fois.</span><span class="sxs-lookup"><span data-stu-id="12146-210">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once.</span></span> <span data-ttu-id="12146-211">Si vous utilisez un objet de stratégie de groupe (GPO) pour mettre à jour le registre, vous devez définir l’objet pour créer une nouvelle valeur au lieu de mettre à jour les données de la valeur.</span><span class="sxs-lookup"><span data-stu-id="12146-211">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="12146-212">Lorsque l’objet de stratégie de groupe est appliqué, si la nouvelle valeur n’existe pas, l’objet de stratégie de groupe le crée et définit la valeur sur 0.</span><span class="sxs-lookup"><span data-stu-id="12146-212">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>

<span data-ttu-id="12146-213">La procédure suivante décrit comment modifier le registre afin que l’expérience client Lync soit affichée la première fois qu’un utilisateur lance Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="12146-213">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business.</span></span> <span data-ttu-id="12146-214">Vous pouvez également utiliser cette procédure pour mettre à jour le registre afin de désactiver le didacticiel de l’écran d’accueil, comme décrit précédemment.</span><span class="sxs-lookup"><span data-stu-id="12146-214">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>

<span data-ttu-id="12146-215">**Pour créer l’objet GPO**</span><span class="sxs-lookup"><span data-stu-id="12146-215">**To create the GPO**</span></span>

1.  <span data-ttu-id="12146-216">Démarrez la **console de gestion des stratégies de groupe**.</span><span class="sxs-lookup"><span data-stu-id="12146-216">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="12146-217">Pour plus d’informations sur l’utilisation de la console de gestion des stratégies de groupe, voir [console de gestion des stratégies de groupe](https://go.microsoft.com/fwlink/?linkid=532759).</span><span class="sxs-lookup"><span data-stu-id="12146-217">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?linkid=532759).</span></span>

2.  <span data-ttu-id="12146-218">Cliquez avec le bouton droit sur le nœud **objets de stratégie de groupe** et sélectionnez **nouveau** dans le menu.</span><span class="sxs-lookup"><span data-stu-id="12146-218">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>

3.  <span data-ttu-id="12146-219">Dans la boîte de dialogue **nouvel objet GPO** , entrez un nom pour l’objet de stratégie de groupe, par exemple, **MakeLyncDefaultUI**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="12146-219">In the **New GPO** dialog, enter a name for the GPO, for example, **MakeLyncDefaultUI**, and then click **OK**.</span></span>

4.  <span data-ttu-id="12146-220">Cliquez avec le bouton droit sur le nouvel objet GPO que vous venez de créer, puis sélectionnez **modifier** dans le menu.</span><span class="sxs-lookup"><span data-stu-id="12146-220">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>

5.  <span data-ttu-id="12146-221">Dans l' **éditeur de gestion des stratégies de groupe**, développez **Configuration utilisateur**, **Préférences**, **Paramètres Windows**, puis sélectionnez le nœud **Registre** .</span><span class="sxs-lookup"><span data-stu-id="12146-221">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>

6.  <span data-ttu-id="12146-222">Cliquez avec le bouton droit sur le nœud de **Registre** , puis sélectionnez **nouvel** \> **élément de Registre**.</span><span class="sxs-lookup"><span data-stu-id="12146-222">Right-click on the **Registry** node, and then select **New** \> **Registry Item**.</span></span>

7.  <span data-ttu-id="12146-223">Dans la boîte de dialogue **nouvelles propriétés de Registre** , mettez à jour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="12146-223">On the **New Registry Properties** dialog, update the following:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="12146-224">Champ</span><span class="sxs-lookup"><span data-stu-id="12146-224">Field</span></span></th>
    <th><span data-ttu-id="12146-225">Valeur à sélectionner ou entrer</span><span class="sxs-lookup"><span data-stu-id="12146-225">Value to select or enter</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="12146-226"><strong>Action</strong></span><span class="sxs-lookup"><span data-stu-id="12146-226"><strong>Action</strong></span></span></p></td>
    <td><p><span data-ttu-id="12146-227"><strong>Create</strong></span><span class="sxs-lookup"><span data-stu-id="12146-227"><strong>Create</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="12146-228"><strong>Ruche</strong></span><span class="sxs-lookup"><span data-stu-id="12146-228"><strong>Hive</strong></span></span></p></td>
    <td><p><span data-ttu-id="12146-229">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="12146-229">HKEY_CURRENT_USER</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="12146-230"><strong>Chemin d’accès à la clé</strong></span><span class="sxs-lookup"><span data-stu-id="12146-230"><strong>Key Path</strong></span></span></p></td>
    <td><p><span data-ttu-id="12146-231">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="12146-231">Software\Microsoft\Office\Lync</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="12146-232"><strong>Nom de la valeur</strong></span><span class="sxs-lookup"><span data-stu-id="12146-232"><strong>Value name</strong></span></span></p></td>
    <td><p><span data-ttu-id="12146-233">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="12146-233">EnableSkypeUI</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="12146-234"><strong>Type de valeur</strong></span><span class="sxs-lookup"><span data-stu-id="12146-234"><strong>Value type</strong></span></span></p></td>
    <td><p><span data-ttu-id="12146-235">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="12146-235">REG_BINARY</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="12146-236"><strong>Données de la valeur</strong></span><span class="sxs-lookup"><span data-stu-id="12146-236"><strong>Value data</strong></span></span></p></td>
    <td><p><span data-ttu-id="12146-237">00000000</span><span class="sxs-lookup"><span data-stu-id="12146-237">00000000</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="12146-238">Cliquez sur **OK** pour enregistrer vos modifications, puis fermez l’objet GPO.</span><span class="sxs-lookup"><span data-stu-id="12146-238">Click **OK** to save your changes, and then close the GPO.</span></span>

<span data-ttu-id="12146-239">Ensuite, vous devez lier l’objet de stratégie de groupe que vous avez créé au groupe d’utilisateurs auquel vous souhaitez affecter la stratégie, tel qu’une unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="12146-239">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>

<span data-ttu-id="12146-240">**Pour utiliser l’objet GPO pour affecter la stratégie**</span><span class="sxs-lookup"><span data-stu-id="12146-240">**To use the GPO to assign the policy**</span></span>

1.  <span data-ttu-id="12146-241">Dans la console de gestion des stratégies de groupe, cliquez avec le bouton droit sur l’unité d’organisation à laquelle vous souhaitez affecter la stratégie, puis sélectionnez **lier un objet de stratégie**de groupe existant.</span><span class="sxs-lookup"><span data-stu-id="12146-241">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>

2.  <span data-ttu-id="12146-242">Dans la boîte de dialogue **Sélectionner un objet GPO** , sélectionnez l’objet de stratégie de groupe que vous avez créé, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="12146-242">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>

3.  <span data-ttu-id="12146-243">Sur l’ordinateur de l’utilisateur cible, ouvrez une invite de commandes et tapez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="12146-243">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="12146-244">**gpupdate/target : utilisateur**</span><span class="sxs-lookup"><span data-stu-id="12146-244">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="12146-245">Message « mise à jour de la stratégie... » est affiché pendant l’application de l’objet de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="12146-245">The message "Updating policy..." is displayed while the GPO is applied.</span></span> <span data-ttu-id="12146-246">Une fois l’opération terminée, le message « la mise à jour de la stratégie utilisateur s’est terminée correctement » s’affiche.</span><span class="sxs-lookup"><span data-stu-id="12146-246">When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>

4.  <span data-ttu-id="12146-247">Depuis l'invite de commandes, entrez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="12146-247">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="12146-248">**gpresult/r**</span><span class="sxs-lookup"><span data-stu-id="12146-248">**gpresult /r**</span></span>
    
    <span data-ttu-id="12146-249">Vous devriez voir « objets de stratégie de groupe affectés » avec le nom de l’objet de stratégie de groupe que vous avez créé ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="12146-249">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>

<span data-ttu-id="12146-250">Vous pouvez également vérifier que l’objet de stratégie de groupe a correctement mis à jour le registre sur l’ordinateur d’un utilisateur en examinant le registre.</span><span class="sxs-lookup"><span data-stu-id="12146-250">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="12146-251">Ouvrez l’éditeur du Registre et accédez à la clé \*\* \[ HKEY \_ Current \_ User \\ Software \\ Microsoft \\ Office \\ Lync \] \*\* .</span><span class="sxs-lookup"><span data-stu-id="12146-251">Open Registry Editor and navigate to the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key.</span></span> <span data-ttu-id="12146-252">Si l’objet GPO a correctement mis à jour le registre, vous verrez une valeur nommée EnableSkypeUI avec une valeur de 0.</span><span class="sxs-lookup"><span data-stu-id="12146-252">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

