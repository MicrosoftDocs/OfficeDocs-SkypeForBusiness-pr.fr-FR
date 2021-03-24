---
title: Configurer l’expérience client avec Skype Entreprise 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Résumé : Lisez cette rubrique pour découvrir comment configurer l’expérience client pour les utilisateurs de Skype Entreprise.'
ms.openlocfilehash: 1816ff9af6c8c6e28ca72420f843d224587b2c70
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096008"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a><span data-ttu-id="4d46b-103">Configurer l’expérience client avec Skype Entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="4d46b-103">Configure the client experience with Skype for Business 2015</span></span>
 
<span data-ttu-id="4d46b-104">**Résumé :** Lisez cette rubrique pour découvrir comment configurer l’expérience client pour les utilisateurs de Skype Entreprise 2015.</span><span class="sxs-lookup"><span data-stu-id="4d46b-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business 2015 users.</span></span>
  
<span data-ttu-id="4d46b-105">Skype Entreprise 2015 offre une nouvelle expérience utilisateur basée sur l’expérience produit grand public Skype.</span><span class="sxs-lookup"><span data-stu-id="4d46b-105">Skype for Business 2015 provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="4d46b-106">En plus de toutes les fonctionnalités de Lync, Skype Entreprise propose de nouvelles fonctionnalités avec des contrôles simplifiés et des icônes familières.</span><span class="sxs-lookup"><span data-stu-id="4d46b-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="4d46b-107">Pour plus d’informations sur la nouvelle expérience client, voir [Explorer Skype Entreprise.](https://go.microsoft.com/fwlink/?LinkId=529022)</span><span class="sxs-lookup"><span data-stu-id="4d46b-107">For detailed information about the new client experience, see [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="4d46b-108">Skype Entreprise Server prend en charge la nouvelle expérience client Skype Entreprise, ainsi que l’expérience client Lync.</span><span class="sxs-lookup"><span data-stu-id="4d46b-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="4d46b-109">En tant qu’administrateur, vous pouvez choisir l’expérience client préférée pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4d46b-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="4d46b-110">Par exemple, vous pouvez déployer l’expérience client Lync jusqu’à ce que les utilisateurs de votre organisation soient entièrement formés à la nouvelle expérience Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="4d46b-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="4d46b-111">Ou, si vous n’avez pas encore mis à niveau tous les utilisateurs vers Skype Entreprise Server, vous souhaitez peut-être que tous les utilisateurs ont la même expérience client jusqu’à ce que tous soient mis à niveau vers le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="4d46b-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4d46b-112">Si Skype Entreprise Server et Lync Server sont déployés dans votre organisation, l’expérience client par défaut varie en fonction des versions du serveur et des paramètres d’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4d46b-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="4d46b-113">Lorsque les utilisateurs lancent Skype Entreprise pour la première fois, ils voient toujours l’interface utilisateur de Skype Entreprise, même si vous avez sélectionné l’expérience client Lync.</span><span class="sxs-lookup"><span data-stu-id="4d46b-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="4d46b-114">Après plusieurs minutes, les utilisateurs sont invités à basculer en mode Lync.</span><span class="sxs-lookup"><span data-stu-id="4d46b-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="4d46b-115">Pour plus d’informations, voir **Comportement du client** de premier lancement plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="4d46b-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4d46b-116">L’expérience client Lync 2013 n’est pas une option pour les versions clientes de Skype Entreprise 2016 ou versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="4d46b-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions or later.</span></span> <span data-ttu-id="4d46b-117">Avant d’essayer de configurer votre environnement client pour utiliser le client Lync 2013, vérifiez sa version pour vous assurer qu’elle ne commence pas par le numéro 16 . par exemple : 16.x.x.x.</span><span class="sxs-lookup"><span data-stu-id="4d46b-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="4d46b-118">Configurer l’expérience client</span><span class="sxs-lookup"><span data-stu-id="4d46b-118">Configure the client experience</span></span>

<span data-ttu-id="4d46b-119">Vous pouvez spécifier l’expérience client que les utilisateurs de votre organisation verront à l’aide de l’cmdlet **Set-CSClientPolicy** avec le paramètre EnableSkypeUI :</span><span class="sxs-lookup"><span data-stu-id="4d46b-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="4d46b-120">où XdsIdentity fait référence à la stratégie globale ou à une stratégie de site nommée.</span><span class="sxs-lookup"><span data-stu-id="4d46b-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="4d46b-121">La commande suivante sélectionne l’expérience client Skype Entreprise pour tous les utilisateurs de votre organisation affectés par la stratégie globale (n’oubliez pas, les stratégies spécifiques au site ou à l’utilisateur remplacent la stratégie globale) :</span><span class="sxs-lookup"><span data-stu-id="4d46b-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="4d46b-122">La commande suivante sélectionne l’expérience client Lync pour tous les utilisateurs de votre organisation affectés par la stratégie globale :</span><span class="sxs-lookup"><span data-stu-id="4d46b-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="4d46b-123">La commande suivante sélectionne l’expérience client Skype Entreprise pour tous les utilisateurs du site Redmond :</span><span class="sxs-lookup"><span data-stu-id="4d46b-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="4d46b-124">Si vous souhaitez configurer l’expérience client pour des utilisateurs spécifiques au sein de votre organisation, vous pouvez créer une stratégie utilisateur à l’aide de l’cmdlet **New-CsClientPolicy,** puis affecter la stratégie à des utilisateurs spécifiques à l’aide de l’cmdlet **Grant-CsClientPolicy.**</span><span class="sxs-lookup"><span data-stu-id="4d46b-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="4d46b-125">Par exemple, la commande suivante crée une stratégie de client, SalesClientUI, qui sélectionne l’expérience client Skype Entreprise :</span><span class="sxs-lookup"><span data-stu-id="4d46b-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="4d46b-126">La commande suivante affecte la stratégie, SalesClientUI, à tous les membres du service Sales :</span><span class="sxs-lookup"><span data-stu-id="4d46b-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="4d46b-127">Comportements du client de premier lancement</span><span class="sxs-lookup"><span data-stu-id="4d46b-127">First launch client behaviors</span></span>

<span data-ttu-id="4d46b-128">Par défaut, lorsque les utilisateurs lancent Skype Entreprise 2015 pour la première fois, ils voient toujours l’interface utilisateur de Skype Entreprise, même si vous avez sélectionné l’expérience client Lync en paramétant la valeur du paramètre EnableSkypeUI sur $False comme décrit précédemment.</span><span class="sxs-lookup"><span data-stu-id="4d46b-128">By default, when users launch Skype for Business 2015 for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="4d46b-129">Après plusieurs minutes, les utilisateurs sont invités à basculer en mode Lync.</span><span class="sxs-lookup"><span data-stu-id="4d46b-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="4d46b-130">Si vous souhaitez afficher l’interface utilisateur Lync lorsque les utilisateurs lancent le client Skype Entreprise pour la première fois, suivez ces étapes avant de démarrer pour la première fois après avoir été mis à jour :</span><span class="sxs-lookup"><span data-stu-id="4d46b-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="4d46b-131">Confirmez que la valeur est définie sur $False la stratégie que vous  `EnableSkypeUI` utilisez, comme décrit précédemment.</span><span class="sxs-lookup"><span data-stu-id="4d46b-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="4d46b-132">Mettez à jour le Registre système sur l’ordinateur de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4d46b-132">Update the system registry on the user's computer.</span></span> <span data-ttu-id="4d46b-133">Vous devez le faire avant la première fois que les utilisateurs lancent le client Skype Entreprise, et vous ne devez le faire qu’une seule fois.</span><span class="sxs-lookup"><span data-stu-id="4d46b-133">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="4d46b-134">Pour plus d’informations sur la création d’un objet de stratégie de groupe pour mettre à jour le Registre sur un ordinateur joint à un domaine, consultez la section plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="4d46b-134">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="4d46b-135">Dans la **clé [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync],** créez une **valeur** binaire.</span><span class="sxs-lookup"><span data-stu-id="4d46b-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="4d46b-136">Le **nom de la** valeur doit  **être EnableSkypeUI** et les données de la valeur doivent être définies sur **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="4d46b-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="4d46b-137">La clé doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="4d46b-137">The key should look like the following:</span></span>
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

<span data-ttu-id="4d46b-138">L’interface utilisateur Lync s’affiche désormais lorsque les utilisateurs lancent le client Skype Entreprise pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="4d46b-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="4d46b-139">Contrôler l’affichage du didacticiel sur l’écran d’accueil</span><span class="sxs-lookup"><span data-stu-id="4d46b-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="4d46b-140">Lorsque les utilisateurs ouvrent le client Skype Entreprise, le comportement par défaut consiste à afficher un écran d’accueil qui inclut 7 conseils rapides que la plupart des *utilisateurs demandent.*</span><span class="sxs-lookup"><span data-stu-id="4d46b-140">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="4d46b-141">Vous pouvez désactiver l’affichage de l’écran d’accueil tout en permettant aux utilisateurs d’accéder au didacticiel en ajoutant la valeur de Registre suivante sur l’ordinateur client :</span><span class="sxs-lookup"><span data-stu-id="4d46b-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="4d46b-142">Dans la **clé [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync],** créez une valeur **DWORD (32 bits).**</span><span class="sxs-lookup"><span data-stu-id="4d46b-142">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="4d46b-143">Le **nom de la** valeur doit être **IsBasicTutorialSeenByUser** et les données de la valeur doivent être définies sur **1**. </span><span class="sxs-lookup"><span data-stu-id="4d46b-143">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="4d46b-144">La clé doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="4d46b-144">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="4d46b-145">Désactiver le didacticiel client</span><span class="sxs-lookup"><span data-stu-id="4d46b-145">Turn off the client tutorial</span></span>

<span data-ttu-id="4d46b-146">Si vous ne souhaitez pas que vos utilisateurs puissent accéder au didacticiel, vous pouvez désactiver le didacticiel client avec la valeur de Registre suivante :</span><span class="sxs-lookup"><span data-stu-id="4d46b-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="4d46b-147">Dans la **clé [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync],** créez une valeur **DWORD (32 bits).**</span><span class="sxs-lookup"><span data-stu-id="4d46b-147">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="4d46b-148">Le **nom de la** valeur doit être  **TutorialFeatureEnabled** et les données de la valeur doivent être définies sur **0**.</span><span class="sxs-lookup"><span data-stu-id="4d46b-148">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="4d46b-149">Lync</span><span class="sxs-lookup"><span data-stu-id="4d46b-149">Lync</span></span>
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="4d46b-150">Vous pouvez activer de nouveau le didacticiel en fixant les données **de la** valeur **sur 1**.</span><span class="sxs-lookup"><span data-stu-id="4d46b-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="4d46b-151">Comportements du client par défaut</span><span class="sxs-lookup"><span data-stu-id="4d46b-151">Default client behaviors</span></span>

<span data-ttu-id="4d46b-152">Si Skype Entreprise Server et Lync Server sont déployés dans votre organisation, l’expérience client varie en fonction des versions du serveur et du paramètre d’interface utilisateur Skype.</span><span class="sxs-lookup"><span data-stu-id="4d46b-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="4d46b-153">Le tableau suivant présente l’expérience client initiale basée sur la version du serveur et le paramètre d’interface utilisateur :</span><span class="sxs-lookup"><span data-stu-id="4d46b-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="4d46b-154">**Version du serveur**</span><span class="sxs-lookup"><span data-stu-id="4d46b-154">**Server version**</span></span>|<span data-ttu-id="4d46b-155">**Paramètre EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="4d46b-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="4d46b-156">**Expérience client**</span><span class="sxs-lookup"><span data-stu-id="4d46b-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4d46b-157">Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="4d46b-157">Skype for Business Server</span></span> |<span data-ttu-id="4d46b-158">Par défaut</span><span class="sxs-lookup"><span data-stu-id="4d46b-158">Default</span></span>  <br/> |<span data-ttu-id="4d46b-159">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="4d46b-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="4d46b-160">Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="4d46b-160">Skype for Business Server</span></span>  |<span data-ttu-id="4d46b-161">Vrai</span><span class="sxs-lookup"><span data-stu-id="4d46b-161">True</span></span>  <br/> |<span data-ttu-id="4d46b-162">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="4d46b-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="4d46b-163">Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="4d46b-163">Skype for Business Server</span></span>  |<span data-ttu-id="4d46b-164">False</span><span class="sxs-lookup"><span data-stu-id="4d46b-164">False</span></span>  <br/> |<span data-ttu-id="4d46b-165">Utilisateur invité à basculer en mode Lync (l’utilisateur peut basculer vers Skype Entreprise ultérieurement si vous modifiez le paramètre d’interface utilisateur $true)</span><span class="sxs-lookup"><span data-stu-id="4d46b-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="4d46b-166">Lync Server 2010 ou Lync Server 2013 (avec des correctifs corrects)</span><span class="sxs-lookup"><span data-stu-id="4d46b-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="4d46b-167">Par défaut</span><span class="sxs-lookup"><span data-stu-id="4d46b-167">Default</span></span>  <br/> |<span data-ttu-id="4d46b-168">Utilisateur invité à basculer en mode Lync (l’utilisateur peut basculer vers Skype Entreprise ultérieurement si vous modifiez le paramètre d’interface utilisateur $true)</span><span class="sxs-lookup"><span data-stu-id="4d46b-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="4d46b-169">Lync Server 2010 ou Lync Server 2013 (avec des correctifs corrects)</span><span class="sxs-lookup"><span data-stu-id="4d46b-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="4d46b-170">Vrai</span><span class="sxs-lookup"><span data-stu-id="4d46b-170">True</span></span>  <br/> |<span data-ttu-id="4d46b-171">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="4d46b-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="4d46b-172">Lync Server 2010 ou Lync Server 2013 (avec des correctifs corrects)</span><span class="sxs-lookup"><span data-stu-id="4d46b-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="4d46b-173">False</span><span class="sxs-lookup"><span data-stu-id="4d46b-173">False</span></span>  <br/> |<span data-ttu-id="4d46b-174">Utilisateur invité à basculer en mode Lync (l’utilisateur peut basculer vers Skype Entreprise ultérieurement si vous modifiez le paramètre d’interface utilisateur $true)</span><span class="sxs-lookup"><span data-stu-id="4d46b-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="4d46b-175">Lync Server 2010 ou Lync Server 2013 (sans correctifs)</span><span class="sxs-lookup"><span data-stu-id="4d46b-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="4d46b-176">Par défaut</span><span class="sxs-lookup"><span data-stu-id="4d46b-176">Default</span></span>  <br/> |<span data-ttu-id="4d46b-177">Utilisateur invité à basculer en mode Lync (l’utilisateur ne peut pas basculer vers Skype Entreprise ultérieurement)</span><span class="sxs-lookup"><span data-stu-id="4d46b-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="4d46b-178">Le tableau suivant illustre l’expérience client lorsque l’administrateur modifie le paramètre initial de l’expérience d’interface utilisateur Skype :</span><span class="sxs-lookup"><span data-stu-id="4d46b-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="4d46b-179">**Version du serveur**</span><span class="sxs-lookup"><span data-stu-id="4d46b-179">**Server version**</span></span>|<span data-ttu-id="4d46b-180">**Paramètre EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="4d46b-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="4d46b-181">**Interface utilisateur du client = Lync**</span><span class="sxs-lookup"><span data-stu-id="4d46b-181">**Client UI = Lync**</span></span>|<span data-ttu-id="4d46b-182">**Interface utilisateur du client = Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="4d46b-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4d46b-183">Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="4d46b-183">Skype for Business Server</span></span> |<span data-ttu-id="4d46b-184">Vrai</span><span class="sxs-lookup"><span data-stu-id="4d46b-184">True</span></span>  <br/> |<span data-ttu-id="4d46b-185">Utilisateur invité à basculer vers Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="4d46b-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="4d46b-186">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="4d46b-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="4d46b-187">Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="4d46b-187">Skype for Business Server</span></span> |<span data-ttu-id="4d46b-188">False</span><span class="sxs-lookup"><span data-stu-id="4d46b-188">False</span></span>  <br/> |<span data-ttu-id="4d46b-189">Mode Lync</span><span class="sxs-lookup"><span data-stu-id="4d46b-189">Lync mode</span></span>  <br/> |<span data-ttu-id="4d46b-190">Utilisateur invité à basculer en mode Lync</span><span class="sxs-lookup"><span data-stu-id="4d46b-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="4d46b-191">Lync Server 2010 ou Lync Server 2013 (avec des correctifs corrects)</span><span class="sxs-lookup"><span data-stu-id="4d46b-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="4d46b-192">Vrai</span><span class="sxs-lookup"><span data-stu-id="4d46b-192">True</span></span>  <br/> |<span data-ttu-id="4d46b-193">Utilisateur invité à basculer vers Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="4d46b-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="4d46b-194">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="4d46b-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="4d46b-195">Lync Server 2010 ou Lync Server 2013 (avec des correctifs corrects)</span><span class="sxs-lookup"><span data-stu-id="4d46b-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="4d46b-196">False</span><span class="sxs-lookup"><span data-stu-id="4d46b-196">False</span></span>  <br/> |<span data-ttu-id="4d46b-197">Mode Lync</span><span class="sxs-lookup"><span data-stu-id="4d46b-197">Lync mode</span></span>  <br/> |<span data-ttu-id="4d46b-198">Utilisateur invité à basculer en mode Lync</span><span class="sxs-lookup"><span data-stu-id="4d46b-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="4d46b-199">Lync Server 2010 ou Lync Server 2013 (sans correctifs)</span><span class="sxs-lookup"><span data-stu-id="4d46b-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="4d46b-200">Par défaut</span><span class="sxs-lookup"><span data-stu-id="4d46b-200">Default</span></span>  <br/> |<span data-ttu-id="4d46b-201">Mode Lync (basculement vers Skype Entreprise impossible)</span><span class="sxs-lookup"><span data-stu-id="4d46b-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="4d46b-202">Mode Lync (basculement vers Skype Entreprise impossible)</span><span class="sxs-lookup"><span data-stu-id="4d46b-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="4d46b-203">Les versions de correctif requises pour gérer la configuration du client Skype Entreprise sont :</span><span class="sxs-lookup"><span data-stu-id="4d46b-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="4d46b-204">Lync Server 2010 - Mise à jour cumulative de février 2015 (4.0.7577.710) pour Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4d46b-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="4d46b-205">Pour plus d’informations, [voir Mises à jour pour Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span><span class="sxs-lookup"><span data-stu-id="4d46b-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="4d46b-206">Lync Server 2013 - Mise à jour cumulative de décembre 2014 (5.0.8308.857) pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4d46b-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="4d46b-207">Pour plus d’informations, [voir Mises à jour pour Lync Server 2013.](https://go.microsoft.com/fwlink/p/?LinkId=532772)</span><span class="sxs-lookup"><span data-stu-id="4d46b-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="4d46b-208">Créer un objet de stratégie de groupe pour modifier le Registre sur un ordinateur joint à un domaine</span><span class="sxs-lookup"><span data-stu-id="4d46b-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="4d46b-209">La mise à jour du Registre pour afficher l’expérience client Lync la première fois qu’un utilisateur lance le client Skype Entreprise 2015 ne doit être effectuée qu’une seule fois.</span><span class="sxs-lookup"><span data-stu-id="4d46b-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business 2015 client should be done only once.</span></span> <span data-ttu-id="4d46b-210">Si vous utilisez un objet de stratégie de groupe (GPO) pour mettre à jour le Registre, vous devez définir l’objet pour créer une valeur au lieu de mettre à jour les données de la valeur.</span><span class="sxs-lookup"><span data-stu-id="4d46b-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="4d46b-211">Lorsque l’GPO est appliqué, si la nouvelle valeur n’existe pas, l’objectif de groupe la crée et lui donne la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="4d46b-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="4d46b-212">La procédure suivante décrit comment modifier le Registre afin que l’expérience client Lync s’affiche la première fois qu’un utilisateur lance le client Skype Entreprise 2015.</span><span class="sxs-lookup"><span data-stu-id="4d46b-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business 2015 client.</span></span> <span data-ttu-id="4d46b-213">Vous pouvez également utiliser cette procédure pour mettre à jour le Registre afin de désactiver le didacticiel sur l’écran d’accueil comme décrit précédemment.</span><span class="sxs-lookup"><span data-stu-id="4d46b-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="4d46b-214">Pour créer l’GPO</span><span class="sxs-lookup"><span data-stu-id="4d46b-214">To create the GPO</span></span>

1. <span data-ttu-id="4d46b-215">Démarrez la **console de gestion des stratégies de groupe.**</span><span class="sxs-lookup"><span data-stu-id="4d46b-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="4d46b-216">Pour plus d’informations sur l’utilisation de la Console de gestion des stratégies de groupe, voir La Console de [gestion des stratégies de groupe.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="4d46b-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11)).</span></span>
    
2. <span data-ttu-id="4d46b-217">Cliquez avec le bouton droit sur le nœud **Objets de stratégie de** groupe et sélectionnez **Nouveau** dans le menu.</span><span class="sxs-lookup"><span data-stu-id="4d46b-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="4d46b-218">Dans la boîte de dialogue Nouvel **GPO,** entrez un nom pour l’GPO, par exemple, MakeLyncDefaultUI, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d46b-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="4d46b-219">Cliquez avec le bouton droit sur le nouvel GPO que vous avez créé, puis sélectionnez **Modifier** dans le menu.</span><span class="sxs-lookup"><span data-stu-id="4d46b-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="4d46b-220">Dans **l’Éditeur de gestion des** stratégies de groupe, développez **Configuration** **utilisateur,** Développez Préférences, Développez **Paramètres Windows,** puis sélectionnez le nœud **du** Registre.</span><span class="sxs-lookup"><span data-stu-id="4d46b-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="4d46b-221">Cliquez avec le bouton droit **sur le** nœud du Registre, puis sélectionnez **Nouvel** élément  >  **de Registre.**</span><span class="sxs-lookup"><span data-stu-id="4d46b-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="4d46b-222">Dans la **boîte de dialogue Nouvelles propriétés du** Registre, mettez à jour les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4d46b-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="4d46b-223">**Field**</span><span class="sxs-lookup"><span data-stu-id="4d46b-223">**Field**</span></span>|<span data-ttu-id="4d46b-224">**Valeur à sélectionner ou à entrer**</span><span class="sxs-lookup"><span data-stu-id="4d46b-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="4d46b-225">**Action**</span><span class="sxs-lookup"><span data-stu-id="4d46b-225">**Action**</span></span> <br/> |<span data-ttu-id="4d46b-226">**Créer**</span><span class="sxs-lookup"><span data-stu-id="4d46b-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="4d46b-227">**Ruche**</span><span class="sxs-lookup"><span data-stu-id="4d46b-227">**Hive**</span></span> <br/> | <span data-ttu-id="4d46b-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="4d46b-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="4d46b-229">**Chemin d’accès de la touche**</span><span class="sxs-lookup"><span data-stu-id="4d46b-229">**Key Path**</span></span> <br/> |<span data-ttu-id="4d46b-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="4d46b-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="4d46b-231">**Nom de la valeur**</span><span class="sxs-lookup"><span data-stu-id="4d46b-231">**Value name**</span></span> <br/> |<span data-ttu-id="4d46b-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="4d46b-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="4d46b-233">**Type de valeur**</span><span class="sxs-lookup"><span data-stu-id="4d46b-233">**Value type**</span></span> <br/> |<span data-ttu-id="4d46b-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="4d46b-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="4d46b-235">**Données de valeur**</span><span class="sxs-lookup"><span data-stu-id="4d46b-235">**Value data**</span></span> <br/> |<span data-ttu-id="4d46b-236">00000000</span><span class="sxs-lookup"><span data-stu-id="4d46b-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="4d46b-237">Cliquez **sur OK** pour enregistrer vos modifications, puis fermez l’GPO.</span><span class="sxs-lookup"><span data-stu-id="4d46b-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="4d46b-238">Ensuite, vous devez lier l’GPO que vous avez créé au groupe d’utilisateurs à qui vous souhaitez affecter la stratégie, tel qu’une ou plusieurs.</span><span class="sxs-lookup"><span data-stu-id="4d46b-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="4d46b-239">Pour utiliser l’GPO pour affecter la stratégie</span><span class="sxs-lookup"><span data-stu-id="4d46b-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="4d46b-240">Dans la console de gestion des stratégies de groupe, cliquez avec le bouton droit sur l’ou à qui vous souhaitez affecter la stratégie, puis sélectionnez Lien vers un **GPO existant.**</span><span class="sxs-lookup"><span data-stu-id="4d46b-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="4d46b-241">Dans la boîte de dialogue Sélectionner **un GPO,** sélectionnez l’GPO que vous avez créé, puis **sélectionnez OK.**</span><span class="sxs-lookup"><span data-stu-id="4d46b-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="4d46b-242">Sur l’ordinateur de l’utilisateur cible, ouvrez une invite de commandes et tapez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4d46b-242">On the target user's computer, open a command prompt and type the following command:</span></span>
       
```console
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. <span data-ttu-id="4d46b-243">Depuis l'invite de commandes, entrez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4d46b-243">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="4d46b-244">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="4d46b-244">**gpresult /r**</span></span>
    
    <span data-ttu-id="4d46b-245">Vous devez voir « Objets de stratégie de groupe affectés » avec le nom de l’objet de stratégie de groupe que vous avez créé, affiché ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="4d46b-245">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="4d46b-246">Vous pouvez également vérifier que l’GPO a correctement mis à jour le Registre sur l’ordinateur d’un utilisateur en examinant le Registre.</span><span class="sxs-lookup"><span data-stu-id="4d46b-246">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="4d46b-247">Ouvrez l’Éditeur du Registre et accédez à la **clé [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync].**</span><span class="sxs-lookup"><span data-stu-id="4d46b-247">Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key.</span></span> <span data-ttu-id="4d46b-248">Si l’GPO a correctement mis à jour le Registre, vous verrez une valeur nommée EnableSkypeUI avec la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="4d46b-248">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
