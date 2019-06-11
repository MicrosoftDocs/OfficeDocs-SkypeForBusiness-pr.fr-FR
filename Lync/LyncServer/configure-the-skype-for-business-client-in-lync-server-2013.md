---
title: Configurer le client Skype entreprise dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fa863fd1775fbc2a726806f2dd4fff5fed5dbfd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a><span data-ttu-id="b052d-102">Configuration de l’expérience client avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="b052d-102">Configure the client experience with Skype for Business</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b052d-103">_**Dernière modification de la rubrique:** 2015-09-17_</span><span class="sxs-lookup"><span data-stu-id="b052d-103">_**Topic Last Modified:** 2015-09-17_</span></span>

<span data-ttu-id="b052d-104">**Résumé:** Cette rubrique décrit comment configurer l’utilisation du client pour les utilisateurs de clients Skype entreprise dans un environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b052d-104">**Summary:** This topic describes how to configure the client experience for Skype for Business client users in a Lync Server 2013 environment.</span></span> <span data-ttu-id="b052d-105">Vous pouvez configurer l’interface client uniquement si vous exécutez Lync Server 2013 avec la mise à jour cumulative 2014 de décembre (5.0.8308.857) ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="b052d-105">You can configure the client experience only if you are running Lync Server 2013 with the December 2014 Cumulative Update (5.0.8308.857) or later installed.</span></span> <span data-ttu-id="b052d-106">Pour plus d’informations sur la mise à jour de Lync Server 2013, voir [mises à jour de Lync server 2013](http://go.microsoft.com/fwlink/p/?linkid=532651).</span><span class="sxs-lookup"><span data-stu-id="b052d-106">For information about updating Lync Server 2013, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532651).</span></span>

<span data-ttu-id="b052d-107">Skype entreprise fournit une nouvelle interface utilisateur qui repose sur l’utilisation des produits Skype.</span><span class="sxs-lookup"><span data-stu-id="b052d-107">Skype for Business provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="b052d-108">Outre l’ensemble des fonctionnalités de Lync, Skype entreprise fournit de nouvelles fonctionnalités avec des contrôles simplifiés et des icônes familières.</span><span class="sxs-lookup"><span data-stu-id="b052d-108">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="b052d-109">Pour plus d’informations sur la nouvelle interface client, voir [Lync devient Skype entreprise--](http://go.microsoft.com/fwlink/?linkid=529022)nouveautés.</span><span class="sxs-lookup"><span data-stu-id="b052d-109">For detailed information about the new client experience, see [Lync is now Skype for Business -- see what's new](http://go.microsoft.com/fwlink/?linkid=529022).</span></span>

<span data-ttu-id="b052d-110">Lync Server 2013 prend en charge la nouvelle interface client Skype entreprise, ainsi que l’interface du client Lync.</span><span class="sxs-lookup"><span data-stu-id="b052d-110">Lync Server 2013 supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="b052d-111">En tant qu’administrateur, vous pouvez choisir la meilleure expérience client pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b052d-111">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="b052d-112">Par exemple, vous souhaiterez peut-être déployer l’interface du client Lync jusqu’à ce que les utilisateurs de votre organisation aient pleinement formé la nouvelle interface Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="b052d-112">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="b052d-113">Ou bien, si vous n’avez pas encore effectué la mise à niveau de tous les utilisateurs vers Skype entreprise Server 2015, vous souhaiterez peut-être que tous les utilisateurs disposent de la même interface utilisateur jusqu’à ce qu’ils soient mis à niveau vers le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="b052d-113">Or, if you have not yet upgraded all users to Skype for Business Server 2015, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b052d-114">Si votre organisation utilise à la fois Skype entreprise Server Server 2015 et Lync Server 2013, l’interface client par défaut varie en fonction des versions de serveur et des paramètres d’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b052d-114">If your organization has both Skype for Business Server 2015 and Lync Server 2013 deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="b052d-115">Lorsque les utilisateurs lancent Skype entreprise pour la première fois, l’interface utilisateur de Skype entreprise est toujours affichée, même si vous avez sélectionné l’interface utilisateur de Lync.</span><span class="sxs-lookup"><span data-stu-id="b052d-115">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync user interface.</span></span> <span data-ttu-id="b052d-116">Après plusieurs minutes, l’utilisateur est invité à basculer vers le mode Lync.</span><span class="sxs-lookup"><span data-stu-id="b052d-116">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="b052d-117">Pour plus d’informations, voir <STRONG>Comportements client au premier lancement</STRONG> dans la suite de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="b052d-117">For more information, see <STRONG>First launch client behavior</STRONG> later in this topic.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b052d-118">L’interface du client 2013 de Lync n’est pas disponible pour les versions clientes de Skype entreprise 2016.</span><span class="sxs-lookup"><span data-stu-id="b052d-118">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="b052d-119">Avant de configurer votre environnement client pour qu’il utilise le client 2013 Lync, vérifiez la version du client pour vous assurer qu’il ne commence pas par le numéro 16; par exemple: 16. x.x.x.</span><span class="sxs-lookup"><span data-stu-id="b052d-119">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span>



</div>

<div>

## <a name="configure-the-client-experience"></a><span data-ttu-id="b052d-120">Configure the client experience</span><span class="sxs-lookup"><span data-stu-id="b052d-120">Configure the client experience</span></span>

<span data-ttu-id="b052d-121">Vous pouvez spécifier l’utilisation du client que les utilisateurs de votre organisation verront à l’aide de l’applet de passe **Set-CSClientPolicy** avec le paramètre EnableSkypeUI.</span><span class="sxs-lookup"><span data-stu-id="b052d-121">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter.</span></span> <span data-ttu-id="b052d-122">La commande suivante sélectionne l’interface client Skype entreprise pour tous les utilisateurs de votre organisation concernés par la politique globale (n’oubliez pas que les stratégies de site ou d’utilisateur remplacent la stratégie globale):</span><span class="sxs-lookup"><span data-stu-id="b052d-122">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

<span data-ttu-id="b052d-123">La commande suivante sélectionne l’interface du client Lync pour tous les utilisateurs de votre organisation concernés par la stratégie globale:</span><span class="sxs-lookup"><span data-stu-id="b052d-123">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

<span data-ttu-id="b052d-124">La commande suivante sélectionne l’interface client Skype entreprise pour tous les utilisateurs du site de Redmond:</span><span class="sxs-lookup"><span data-stu-id="b052d-124">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

<span data-ttu-id="b052d-125">Si vous voulez configurer l’utilisation du client pour des utilisateurs spécifiques au sein de votre organisation, vous pouvez créer une nouvelle stratégie d’utilisateur à l’aide de l’applet **de nouvelle** applet de CsClientPolicy, puis affecter la stratégie à des utilisateurs spécifiques à l’aide de l’applet de passe **CsClientPolicy** applet.</span><span class="sxs-lookup"><span data-stu-id="b052d-125">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>

<span data-ttu-id="b052d-126">Par exemple, la commande suivante crée une nouvelle stratégie client, SalesClientUI, qui sélectionne l’interface du client Skype entreprise:</span><span class="sxs-lookup"><span data-stu-id="b052d-126">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

<span data-ttu-id="b052d-127">La commande suivante affecte la stratégie, SalesClientUI, à tous les membres du service commercial :</span><span class="sxs-lookup"><span data-stu-id="b052d-127">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="b052d-128">Comportements client au premier lancement</span><span class="sxs-lookup"><span data-stu-id="b052d-128">First launch client behaviors</span></span>

<span data-ttu-id="b052d-129">Par défaut, lorsque les utilisateurs lancent Skype entreprise pour la première fois, l’interface utilisateur de Skype entreprise est toujours affichée, même si vous avez sélectionné l’environnement du client Lync en définissant la valeur du paramètre EnableSkypeUI sur $False comme décrit précédemment .</span><span class="sxs-lookup"><span data-stu-id="b052d-129">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="b052d-130">Après quelques minutes, les utilisateurs sont invités à passer en mode Lync.</span><span class="sxs-lookup"><span data-stu-id="b052d-130">After several minutes, users will then be asked to switch to Lync mode.</span></span>

<span data-ttu-id="b052d-131">Si vous souhaitez afficher l'interface utilisateur Lync lorsque les utilisateurs lancent le client Skype Entreprise pour la première fois, suivez cette procédure avant le premier démarrage du client après la mise à jour :</span><span class="sxs-lookup"><span data-stu-id="b052d-131">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>

1.  <span data-ttu-id="b052d-132">Vérifiez que la valeur de `EnableSkypeUI` est définie sur $false dans la stratégie que vous utilisez, comme décrit précédemment.</span><span class="sxs-lookup"><span data-stu-id="b052d-132">Confirm that the value of `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>

2.  <span data-ttu-id="b052d-p108">Mettez à jour le registre système sur l'ordinateur de l'utilisateur. Vous devez le faire avant que les utilisateurs lancent le client Skype Entreprise la première fois et vous ne devez effectuer cette opération qu'une seule fois. Pour plus d'informations sur la création d'un objet de stratégie de groupe pour mettre à jour le registre sur un ordinateur joint à un domaine, reportez-vous à la section dans la suite de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="b052d-p108">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="b052d-136">Dans la \*\* \[clé\_Microsoft\_\\Office\\\\Lync\\\] logiciel de l’utilisateur actuel\*\* , créez une valeur **binaire** .</span><span class="sxs-lookup"><span data-stu-id="b052d-136">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="b052d-137">Le **nom de la valeur** doit être **EnableSkypeUI** et les **données de la valeur** doivent être définies sur la valeur **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="b052d-137">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="b052d-138">La clé doit se présenter comme celle-ci :</span><span class="sxs-lookup"><span data-stu-id="b052d-138">The key should look like the following:</span></span>
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

<span data-ttu-id="b052d-139">L'interface utilisateur de Lync s'affiche maintenant lorsque les utilisateurs lancent le client Skype Entreprise pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="b052d-139">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="b052d-140">Contrôler l’affichage du didacticiel de l’écran d’accueil</span><span class="sxs-lookup"><span data-stu-id="b052d-140">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="b052d-141">Lorsque les utilisateurs ouvrent le client Skype entreprise, le comportement par défaut consiste à afficher un écran d’accueil incluant *7 conseils rapides pour la plupart des personnes*.</span><span class="sxs-lookup"><span data-stu-id="b052d-141">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="b052d-142">Vous pouvez désactiver l'affichage de l'écran d'accueil, mais permettre quand même aux utilisateurs d'accéder au didacticiel en ajoutant la valeur de registre ci-dessous sur l'ordinateur client :</span><span class="sxs-lookup"><span data-stu-id="b052d-142">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>

<span data-ttu-id="b052d-143">Dans la \*\* \[clé\_Microsoft\_\\Office\\\\15,0\\\\du logiciel de l’utilisateur HKEY actuel, créez une nouvelle valeur DWORD (32 bits\] \*\* **)**.</span><span class="sxs-lookup"><span data-stu-id="b052d-143">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="b052d-144">Le **nom de la valeur** doit être **IsBasicTutorialSeenByUser** et les **données de valeur** doivent être définies sur **1**.</span><span class="sxs-lookup"><span data-stu-id="b052d-144">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>

<span data-ttu-id="b052d-145">La clé doit se présenter comme celle-ci :</span><span class="sxs-lookup"><span data-stu-id="b052d-145">The key should look like the following:</span></span>

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="b052d-146">Désactivation du didacticiel client</span><span class="sxs-lookup"><span data-stu-id="b052d-146">Turn off the client tutorial</span></span>

<span data-ttu-id="b052d-147">Si vous ne voulez pas que vos utilisateurs puissent accéder au didacticiel, vous pouvez désactiver le didacticiel du client avec la valeur de registre suivante :</span><span class="sxs-lookup"><span data-stu-id="b052d-147">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>

<span data-ttu-id="b052d-148">Dans la \*\* \[clé\_Microsoft\_\\Office\\\\15,0\\\\du logiciel de l’utilisateur HKEY actuel, créez une nouvelle valeur DWORD (32 bits\] \*\* **)**.</span><span class="sxs-lookup"><span data-stu-id="b052d-148">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="b052d-149">Le **nom de la valeur** doit être **TutorialFeatureEnabled** et les **données de valeur** doivent être définies sur **0**.</span><span class="sxs-lookup"><span data-stu-id="b052d-149">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>

    "TutorialFeatureEnabled"=dword:00000000

<span data-ttu-id="b052d-150">Vous pouvez réactiver le didacticiel en définissant les **données de valeur** sur **1**.</span><span class="sxs-lookup"><span data-stu-id="b052d-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>

</div>

</div>

<div>

## <a name="default-client-experiences"></a><span data-ttu-id="b052d-151">Expériences client par défaut</span><span class="sxs-lookup"><span data-stu-id="b052d-151">Default client experiences</span></span>

<span data-ttu-id="b052d-152">Si votre organisation utilise à la fois Skype entreprise Server Server 2015 et Lync Server, l’environnement client varie en fonction des versions de serveur et du paramètre d’interface utilisateur de Skype.</span><span class="sxs-lookup"><span data-stu-id="b052d-152">If your organization has both Skype for Business Server 2015 and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="b052d-153">Le tableau ci-dessous montre l’expérience client initiale en fonction de la version du serveur et du paramètre de l’interface utilisateur :</span><span class="sxs-lookup"><span data-stu-id="b052d-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b052d-154">Version du serveur</span><span class="sxs-lookup"><span data-stu-id="b052d-154">Server version</span></span></p></th>
<th><p><span data-ttu-id="b052d-155">Paramètre EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="b052d-155">EnableSkypeUI setting</span></span></p></th>
<th><p><span data-ttu-id="b052d-156">Expérience client</span><span class="sxs-lookup"><span data-stu-id="b052d-156">Client experience</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b052d-157">Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="b052d-157">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="b052d-158">Par défaut</span><span class="sxs-lookup"><span data-stu-id="b052d-158">Default</span></span></p></td>
<td><p><span data-ttu-id="b052d-159">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="b052d-159">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b052d-160">Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="b052d-160">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="b052d-161">True</span><span class="sxs-lookup"><span data-stu-id="b052d-161">True</span></span></p></td>
<td><p><span data-ttu-id="b052d-162">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="b052d-162">Skype for Business</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b052d-163">Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="b052d-163">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="b052d-164">False</span><span class="sxs-lookup"><span data-stu-id="b052d-164">False</span></span></p></td>
<td><p><span data-ttu-id="b052d-165">Utilisateur invité à basculer vers le mode Lync (l’utilisateur peut basculer vers Skype entreprise plus tard si vous modifiez le paramètre de l’interface utilisateur en $true)</span><span class="sxs-lookup"><span data-stu-id="b052d-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b052d-166">Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)</span><span class="sxs-lookup"><span data-stu-id="b052d-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="b052d-167">Par défaut</span><span class="sxs-lookup"><span data-stu-id="b052d-167">Default</span></span></p></td>
<td><p><span data-ttu-id="b052d-168">Utilisateur invité à basculer vers le mode Lync (l’utilisateur peut basculer vers Skype entreprise plus tard si vous modifiez le paramètre de l’interface utilisateur en $true)</span><span class="sxs-lookup"><span data-stu-id="b052d-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b052d-169">Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)</span><span class="sxs-lookup"><span data-stu-id="b052d-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="b052d-170">True</span><span class="sxs-lookup"><span data-stu-id="b052d-170">True</span></span></p></td>
<td><p><span data-ttu-id="b052d-171">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="b052d-171">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b052d-172">Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)</span><span class="sxs-lookup"><span data-stu-id="b052d-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="b052d-173">False</span><span class="sxs-lookup"><span data-stu-id="b052d-173">False</span></span></p></td>
<td><p><span data-ttu-id="b052d-174">Utilisateur invité à basculer vers le mode Lync (l’utilisateur peut basculer vers Skype entreprise plus tard si vous modifiez le paramètre de l’interface utilisateur en $true)</span><span class="sxs-lookup"><span data-stu-id="b052d-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b052d-175">Lync Server 2010 ou Lync Server 2013 (sans correctifs)</span><span class="sxs-lookup"><span data-stu-id="b052d-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="b052d-176">Par défaut</span><span class="sxs-lookup"><span data-stu-id="b052d-176">Default</span></span></p></td>
<td><p><span data-ttu-id="b052d-177">Utilisateur invité à basculer vers l’utilisation du client Lync (l’utilisateur ne peut pas basculer vers Skype entreprise plus tard)</span><span class="sxs-lookup"><span data-stu-id="b052d-177">User asked to switch to Lync client experience (user cannot switch to Skype for Business later)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b052d-178">Le tableau suivant indique l’environnement client lorsque l’administrateur modifie le paramètre initial de l’interface utilisateur de Skype:</span><span class="sxs-lookup"><span data-stu-id="b052d-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b052d-179">Version du serveur</span><span class="sxs-lookup"><span data-stu-id="b052d-179">Server version</span></span></p></th>
<th><p><span data-ttu-id="b052d-180">Paramètre d’interface utilisateur de Skype</span><span class="sxs-lookup"><span data-stu-id="b052d-180">Skype UI setting</span></span></p></th>
<th><p><span data-ttu-id="b052d-181">Interface utilisateur du client = Lync</span><span class="sxs-lookup"><span data-stu-id="b052d-181">Client UI = Lync</span></span></p></th>
<th><p><span data-ttu-id="b052d-182">UI client = Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="b052d-182">Client UI = Skype for Business</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b052d-183">Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="b052d-183">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="b052d-184">True</span><span class="sxs-lookup"><span data-stu-id="b052d-184">True</span></span></p></td>
<td><p><span data-ttu-id="b052d-185">Utilisateur invité à basculer sur Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="b052d-185">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="b052d-186">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="b052d-186">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b052d-187">Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="b052d-187">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="b052d-188">False</span><span class="sxs-lookup"><span data-stu-id="b052d-188">False</span></span></p></td>
<td><p><span data-ttu-id="b052d-189">Interface utilisateur Lync</span><span class="sxs-lookup"><span data-stu-id="b052d-189">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="b052d-190">Utilisateur invité à basculer sur l’interface utilisateur de Lync</span><span class="sxs-lookup"><span data-stu-id="b052d-190">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b052d-191">Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)</span><span class="sxs-lookup"><span data-stu-id="b052d-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="b052d-192">True</span><span class="sxs-lookup"><span data-stu-id="b052d-192">True</span></span></p></td>
<td><p><span data-ttu-id="b052d-193">Utilisateur invité à basculer sur Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="b052d-193">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="b052d-194">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="b052d-194">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b052d-195">Lync Server 2010 ou Lync Server 2013 (avec les correctifs appropriés)</span><span class="sxs-lookup"><span data-stu-id="b052d-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="b052d-196">False</span><span class="sxs-lookup"><span data-stu-id="b052d-196">False</span></span></p></td>
<td><p><span data-ttu-id="b052d-197">Interface utilisateur Lync</span><span class="sxs-lookup"><span data-stu-id="b052d-197">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="b052d-198">Utilisateur invité à basculer sur l’interface utilisateur de Lync</span><span class="sxs-lookup"><span data-stu-id="b052d-198">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b052d-199">Lync Server 2010 ou Lync Server 2013 (sans correctifs)</span><span class="sxs-lookup"><span data-stu-id="b052d-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="b052d-200">Par défaut</span><span class="sxs-lookup"><span data-stu-id="b052d-200">Default</span></span></p></td>
<td><p><span data-ttu-id="b052d-201">Mode Lync (possibilité de basculer vers Skype entreprise)</span><span class="sxs-lookup"><span data-stu-id="b052d-201">Lync mode (cannot switch to Skype for Business)</span></span></p></td>
<td><p><span data-ttu-id="b052d-202">Interface utilisateur Lync (impossible de basculer vers Skype entreprise)</span><span class="sxs-lookup"><span data-stu-id="b052d-202">Lync UI (cannot switch to Skype for Business)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b052d-203">Les versions de correctif requises pour gérer la configuration du client Skype entreprise sont les suivantes:</span><span class="sxs-lookup"><span data-stu-id="b052d-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>

  - <span data-ttu-id="b052d-204">Mise à jour cumulative de Lync Server 2010-février 2015 (4.0.7577.710) pour Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b052d-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="b052d-205">Pour plus d’informations, voir [mises à jour pour Lync Server 2010](http://go.microsoft.com/fwlink/p/?linkid=532771)</span><span class="sxs-lookup"><span data-stu-id="b052d-205">For information, see [Updates for Lync Server 2010](http://go.microsoft.com/fwlink/p/?linkid=532771)</span></span>

  - <span data-ttu-id="b052d-206">Mise à jour cumulative de Lync Server 2013-décembre 2014 (5.0.8308.857) pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b052d-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="b052d-207">Pour plus d’informations, consultez [mises à jour pour Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532772).</span><span class="sxs-lookup"><span data-stu-id="b052d-207">For information, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532772).</span></span>

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="b052d-208">Créer un objet de stratégie de groupe pour modifier le Registre sur un ordinateur joint au domaine</span><span class="sxs-lookup"><span data-stu-id="b052d-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="b052d-p115">La mise à jour du registre pour afficher l'expérience client Lync la première fois qu'un utilisateur lance le client Skype Entreprise ne doit être effectuée qu'une seule fois. Si vous utilisez un objet de stratégie de groupe pour mettre à jour le registre, vous devez définir l'objet pour créer une valeur et non mettre à jour les données d'une valeur. Lorsque l'objet de stratégie de groupe est appliqué, si la nouvelle valeur n'existe pas, l'objet stratégie de groupe la crée et définit les données de valeur sur 0.</span><span class="sxs-lookup"><span data-stu-id="b052d-p115">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once. If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data. When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>

<span data-ttu-id="b052d-p116">La procédure ci-dessous décrit comment modifier le registre afin que l'expérience client Lync s'affiche la première fois qu'un utilisateur lance le client Skype Entreprise. Vous pouvez également utiliser cette procédure pour mettre à jour le registre afin de désactiver l'écran d'accueil du didacticiel, comme indiqué précédemment.</span><span class="sxs-lookup"><span data-stu-id="b052d-p116">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business. You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>

<span data-ttu-id="b052d-214">**Pour créer l’objet GPO**</span><span class="sxs-lookup"><span data-stu-id="b052d-214">**To create the GPO**</span></span>

1.  <span data-ttu-id="b052d-215">Démarrez la **Console de gestion des stratégies de groupe**.</span><span class="sxs-lookup"><span data-stu-id="b052d-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="b052d-216">Pour plus d'informations sur l'utilisation de la Console de gestion des stratégies de groupe, reportez-vous à l'article [Console de gestion des stratégies de groupe](http://go.microsoft.com/fwlink/?linkid=532759).</span><span class="sxs-lookup"><span data-stu-id="b052d-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](http://go.microsoft.com/fwlink/?linkid=532759).</span></span>

2.  <span data-ttu-id="b052d-217">Cliquez avec le bouton droit sur le nœud **Objets de stratégie de groupe** et sélectionnez **Nouveau** dans le menu.</span><span class="sxs-lookup"><span data-stu-id="b052d-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>

3.  <span data-ttu-id="b052d-218">Dans la boîte de dialogue **Nouvel objet GPO**, entrez un nom pour l’objet GPO, par exemple, **MakeLyncDefaultUI**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b052d-218">In the **New GPO** dialog, enter a name for the GPO, for example, **MakeLyncDefaultUI**, and then click **OK**.</span></span>

4.  <span data-ttu-id="b052d-219">Effectuez un clic droit sur le nouvel objet GPO que vous venez de créer, puis sélectionnez **Modifier** dans menu.</span><span class="sxs-lookup"><span data-stu-id="b052d-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>

5.  <span data-ttu-id="b052d-220">Dans **Éditeur de gestion des stratégies de groupe**, développez **Configuration utilisateur**, **Préférences**, **Paramètres Windows**, puis sélectionnez le nœud **Registre**.</span><span class="sxs-lookup"><span data-stu-id="b052d-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>

6.  <span data-ttu-id="b052d-221">Cliquez avec le bouton droit sur le nœud **Registre** , puis sélectionnez **nouvel** \> **élément Registre**.</span><span class="sxs-lookup"><span data-stu-id="b052d-221">Right-click on the **Registry** node, and then select **New** \> **Registry Item**.</span></span>

7.  <span data-ttu-id="b052d-222">Dans la boîte de dialogue **Nouvelles propriétés de Registre**, mettez à jour ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="b052d-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="b052d-223">Champ</span><span class="sxs-lookup"><span data-stu-id="b052d-223">Field</span></span></th>
    <th><span data-ttu-id="b052d-224">Valeur à sélectionner ou entrer</span><span class="sxs-lookup"><span data-stu-id="b052d-224">Value to select or enter</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="b052d-225"><strong>Action</strong></span><span class="sxs-lookup"><span data-stu-id="b052d-225"><strong>Action</strong></span></span></p></td>
    <td><p><span data-ttu-id="b052d-226"><strong>Créer</strong></span><span class="sxs-lookup"><span data-stu-id="b052d-226"><strong>Create</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="b052d-227"><strong>Ruche</strong></span><span class="sxs-lookup"><span data-stu-id="b052d-227"><strong>Hive</strong></span></span></p></td>
    <td><p><span data-ttu-id="b052d-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="b052d-228">HKEY_CURRENT_USER</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="b052d-229"><strong>Chemin d’accès à la clé</strong></span><span class="sxs-lookup"><span data-stu-id="b052d-229"><strong>Key Path</strong></span></span></p></td>
    <td><p><span data-ttu-id="b052d-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="b052d-230">Software\Microsoft\Office\Lync</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="b052d-231"><strong>Nom de la valeur</strong></span><span class="sxs-lookup"><span data-stu-id="b052d-231"><strong>Value name</strong></span></span></p></td>
    <td><p><span data-ttu-id="b052d-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="b052d-232">EnableSkypeUI</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="b052d-233"><strong>Type de la valeur</strong></span><span class="sxs-lookup"><span data-stu-id="b052d-233"><strong>Value type</strong></span></span></p></td>
    <td><p><span data-ttu-id="b052d-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="b052d-234">REG_BINARY</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="b052d-235"><strong>Données de la valeur</strong></span><span class="sxs-lookup"><span data-stu-id="b052d-235"><strong>Value data</strong></span></span></p></td>
    <td><p><span data-ttu-id="b052d-236">00000000</span><span class="sxs-lookup"><span data-stu-id="b052d-236">00000000</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="b052d-237">Cliquez sur **OK** pour enregistrer les modifications, puis fermez l'objet GPO.</span><span class="sxs-lookup"><span data-stu-id="b052d-237">Click **OK** to save your changes, and then close the GPO.</span></span>

<span data-ttu-id="b052d-238">Ensuite, vous devez lier l'objet GPO créé au groupe d'utilisateurs auquel vous voulez affecter la stratégie, par exemple, une unité d'organisation.</span><span class="sxs-lookup"><span data-stu-id="b052d-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>

<span data-ttu-id="b052d-239">**Pour utiliser l’objet GPO pour affecter la stratégie**</span><span class="sxs-lookup"><span data-stu-id="b052d-239">**To use the GPO to assign the policy**</span></span>

1.  <span data-ttu-id="b052d-240">Dans la console de gestion des stratégies de groupe, cliquez avec le bouton droit sur l'unité d'organisation à laquelle vous voulez affecter la stratégie, puis sélectionnez **Lier un objet de stratégie de groupe existant**.</span><span class="sxs-lookup"><span data-stu-id="b052d-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>

2.  <span data-ttu-id="b052d-241">Dans la boîte de dialogue **Sélectionner un objet GPO**, sélectionnez l'objet GPO créé, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="b052d-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>

3.  <span data-ttu-id="b052d-242">Sur l'ordinateur de l'utilisateur cible, ouvrez une invite de commandes et tapez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b052d-242">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="b052d-243">**gpupdate /target:user**</span><span class="sxs-lookup"><span data-stu-id="b052d-243">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="b052d-p117">Le message « mise à jour la stratégie… » s'affiche pendant l'application de l'objet GPO. Au terme de l'opération, le message « La mise à jour de la stratégie utilisateur s'est terminée sans erreur. » s'affiche.</span><span class="sxs-lookup"><span data-stu-id="b052d-p117">The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>

4.  <span data-ttu-id="b052d-246">Dans l'invite de commandes, tapez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b052d-246">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="b052d-247">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="b052d-247">**gpresult /r**</span></span>
    
    <span data-ttu-id="b052d-248">« Objets de stratégie de groupé affectés » doit s'afficher avec le nom de l'objet GPO créé en-dessous.</span><span class="sxs-lookup"><span data-stu-id="b052d-248">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>

<span data-ttu-id="b052d-249">Vous pouvez également vérifier que l'objet de stratégie de groupe a mis à jour le registre sur l'ordinateur de l'utilisateur en examinant le registre.</span><span class="sxs-lookup"><span data-stu-id="b052d-249">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="b052d-250">Ouvrez l’éditeur du Registre et accédez à la clé de \*\* \[\_logiciel\\\\de\\l'\] utilisateur\_\\actuel HKEY Microsoft Office Lync\*\* .</span><span class="sxs-lookup"><span data-stu-id="b052d-250">Open Registry Editor and navigate to the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key.</span></span> <span data-ttu-id="b052d-251">Si l'objet GPO a mis à jour correctement le registre, la valeur nommée EnableSkypeUI s'affiche avec la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="b052d-251">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

