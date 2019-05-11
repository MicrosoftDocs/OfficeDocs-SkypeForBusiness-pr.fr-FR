---
title: Configurer l’expérience du client avec Skype pour Business 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Résumé : Lisez cette rubrique pour savoir comment configurer l’expérience du client pour Skype pour les utilisateurs professionnels.'
ms.openlocfilehash: 65ca5592c3994cfcbb2703d22bc510a3b84b3507
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895390"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a><span data-ttu-id="697f2-103">Configurer l’expérience du client avec Skype pour Business 2015</span><span class="sxs-lookup"><span data-stu-id="697f2-103">Configure the client experience with Skype for Business 2015</span></span>
 
<span data-ttu-id="697f2-104">**Résumé :** Lisez cette rubrique pour savoir comment configurer l’expérience du client pour Skype pour les utilisateurs professionnels 2015.</span><span class="sxs-lookup"><span data-stu-id="697f2-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business 2015 users.</span></span>
  
<span data-ttu-id="697f2-105">Skype pour Business 2015 fournit une nouvelle expérience utilisateur qui est basée sur l’expérience de produit Skype consommateur.</span><span class="sxs-lookup"><span data-stu-id="697f2-105">Skype for Business 2015 provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="697f2-106">En plus de toutes les fonctionnalités de Lync, Skype pour les entreprises fournit de nouvelles fonctionnalités avec des contrôles simplifiés et icônes familières.</span><span class="sxs-lookup"><span data-stu-id="697f2-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="697f2-107">Pour plus d’informations sur l’expérience du client, voir [Explorer de Skype pour les entreprises](https://go.microsoft.com/fwlink/?LinkId=529022).</span><span class="sxs-lookup"><span data-stu-id="697f2-107">For detailed information about the new client experience, see [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="697f2-108">Skype pour Business Server prend en charge la nouvelle Skype pour une expérience client ainsi que l’expérience du client Lync.</span><span class="sxs-lookup"><span data-stu-id="697f2-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="697f2-109">En tant qu’administrateur, vous pouvez choisir la meilleure expérience client pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="697f2-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="697f2-110">Par exemple, vous pouvez souhaiter déployer l’expérience du client Lync jusqu'à ce que les utilisateurs de votre organisation sont formés dans le nouveau Skype pour une expérience.</span><span class="sxs-lookup"><span data-stu-id="697f2-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="697f2-111">Ou, si vous n'avez pas encore mis à niveau tous les utilisateurs Skype pour Business Server, vous pouvez tous les utilisateurs aient la même expérience client jusqu'à ce que toutes les sont mis à niveau vers le nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="697f2-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="697f2-112">Si votre organisation a deux Skype pour Business Server et Lync Server déployé, l’expérience du client par défaut varient selon les versions du serveur et les paramètres de l’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="697f2-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="697f2-113">Lorsque les utilisateurs de lancement Skype pour les entreprises pour la première fois, ils verront toujours le Skype pour l’interface utilisateur d’entreprise : même si vous avez sélectionné l’expérience du client Lync.</span><span class="sxs-lookup"><span data-stu-id="697f2-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="697f2-114">Après quelques minutes, les utilisateurs sont invités à passer en mode Lync.</span><span class="sxs-lookup"><span data-stu-id="697f2-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="697f2-115">Pour plus d’informations, voir **Comportements client au premier lancement** dans la suite de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="697f2-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="697f2-116">L’expérience du client Lync 2013 n’est pas une option de Skype pour les versions clientes de 2016 Business ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="697f2-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions or later.</span></span> <span data-ttu-id="697f2-117">Avant d’essayer de configurer votre environnement client pour utiliser le client Lync 2013, vérifiez la version du client pour vous assurer qu’il ne commence pas par le numéro de 16 ; par exemple : 16.x.x.x.</span><span class="sxs-lookup"><span data-stu-id="697f2-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="697f2-118">Configurer l’expérience client</span><span class="sxs-lookup"><span data-stu-id="697f2-118">Configure the client experience</span></span>

<span data-ttu-id="697f2-119">Vous pouvez spécifier l’expérience client des utilisateurs de votre organisation en utilisant l’applet de commande **Set-CSClientPolicy** avec le paramètre EnableSkypeUI :</span><span class="sxs-lookup"><span data-stu-id="697f2-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="697f2-120">où XdsIdentity renvoie à la stratégie globale ou à une stratégie de site nommé.</span><span class="sxs-lookup"><span data-stu-id="697f2-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="697f2-121">La commande suivante sélectionne le Skype pour une expérience de client d’entreprise pour tous les utilisateurs de votre organisation affectée par la stratégie globale (Souvenez-vous, site ou des stratégies spécifiques à l’utilisateur de la stratégie globale remplacent) :</span><span class="sxs-lookup"><span data-stu-id="697f2-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="697f2-122">La commande suivante sélectionne l’expérience du client Lync pour tous les utilisateurs de votre organisation affectée par la stratégie globale :</span><span class="sxs-lookup"><span data-stu-id="697f2-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="697f2-123">La commande suivante sélectionne le Skype pour une expérience de client d’entreprise pour tous les utilisateurs au sein du site de Redmond :</span><span class="sxs-lookup"><span data-stu-id="697f2-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="697f2-124">Si vous souhaitez configurer l’expérience du client pour des utilisateurs spécifiques au sein de votre organisation, vous pouvez créer une nouvelle stratégie utilisateur à l’aide de l’applet de commande **New-CsClientPolicy** et puis attribuez-les à des utilisateurs spécifiques à l’aide de la **Grant-CsClientPolicy** applet de commande.</span><span class="sxs-lookup"><span data-stu-id="697f2-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="697f2-125">Par exemple, la commande suivante crée une nouvelle stratégie de client, SalesClientUI, qui sélectionne le Skype pour une expérience client :</span><span class="sxs-lookup"><span data-stu-id="697f2-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="697f2-126">La commande suivante affecte la stratégie, SalesClientUI, à tous les membres du service commercial :</span><span class="sxs-lookup"><span data-stu-id="697f2-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="697f2-127">Comportements client au premier lancement</span><span class="sxs-lookup"><span data-stu-id="697f2-127">First launch client behaviors</span></span>

<span data-ttu-id="697f2-128">Par défaut, lorsque les utilisateurs lancer Skype pour Business 2015 pour la première fois, toujours verront le Skype pour l’interface utilisateur d’entreprise : même si vous avez sélectionné l’expérience du client Lync en définissant la valeur du paramètre EnableSkypeUI sur $False comme indiqué précédemment.</span><span class="sxs-lookup"><span data-stu-id="697f2-128">By default, when users launch Skype for Business 2015 for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="697f2-129">Après quelques minutes, les utilisateurs sont invités à passer en mode Lync.</span><span class="sxs-lookup"><span data-stu-id="697f2-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="697f2-130">Si vous souhaitez afficher l'interface utilisateur Lync lorsque les utilisateurs lancent le client Skype Entreprise pour la première fois, suivez cette procédure avant le premier démarrage du client après la mise à jour :</span><span class="sxs-lookup"><span data-stu-id="697f2-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="697f2-131">Vérifiez que la valeur de `EnableSkypeUI` est défini sur $False dans la stratégie que vous utilisez comme décrit précédemment.</span><span class="sxs-lookup"><span data-stu-id="697f2-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="697f2-p106">Mettez à jour le registre système sur l'ordinateur de l'utilisateur. Vous devez le faire avant que les utilisateurs lancent le client Skype Entreprise la première fois et vous ne devez effectuer cette opération qu'une seule fois. Pour plus d'informations sur la création d'un objet de stratégie de groupe pour mettre à jour le registre sur un ordinateur joint à un domaine, reportez-vous à la section dans la suite de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="697f2-p106">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="697f2-135">Dans la clé **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**, créez une nouvelle valeur **Binaire**.</span><span class="sxs-lookup"><span data-stu-id="697f2-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="697f2-136">Le **nom de la valeur** doit être **EnableSkypeUI** et les **données de la valeur** doivent être définies sur la valeur **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="697f2-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="697f2-137">La clé doit se présenter comme celle-ci :</span><span class="sxs-lookup"><span data-stu-id="697f2-137">The key should look like the following:</span></span>
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

<span data-ttu-id="697f2-138">L'interface utilisateur de Lync s'affiche maintenant lorsque les utilisateurs lancent le client Skype Entreprise pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="697f2-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="697f2-139">Contrôler l’affichage du didacticiel de l’écran d’accueil</span><span class="sxs-lookup"><span data-stu-id="697f2-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="697f2-140">Lorsque les utilisateurs ouvrent la Skype pour client d’entreprise, le comportement par défaut consiste à afficher l’écran d’accueil qui inclut *la plupart des personnes 7 conseils rapides demandent*.</span><span class="sxs-lookup"><span data-stu-id="697f2-140">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="697f2-141">Vous pouvez désactiver l'affichage de l'écran d'accueil, mais permettre quand même aux utilisateurs d'accéder au didacticiel en ajoutant la valeur de registre ci-dessous sur l'ordinateur client :</span><span class="sxs-lookup"><span data-stu-id="697f2-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="697f2-p108">Dans la clé **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, créez une nouvelle **valeur (32 bits) DWORD**. Le **nom de la valeur** doit être **IsBasicTutorialSeenByUser**, et les **données de valeur** doivent être définies sur **1**.</span><span class="sxs-lookup"><span data-stu-id="697f2-p108">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="697f2-144">La clé doit ressembler à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="697f2-144">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="697f2-145">Désactivation du didacticiel client</span><span class="sxs-lookup"><span data-stu-id="697f2-145">Turn off the client tutorial</span></span>

<span data-ttu-id="697f2-146">Si vous ne voulez pas que vos utilisateurs puissent accéder au didacticiel, vous pouvez désactiver le didacticiel du client avec la valeur de Registre suivante :</span><span class="sxs-lookup"><span data-stu-id="697f2-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="697f2-p109">Dans la clé **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, créez une nouvelle **valeur (32 bits) DWORD**. Le **nom de la valeur** doit être **TutorialFeatureEnabled**, et les **données de valeur** doivent être définies sur **0**.</span><span class="sxs-lookup"><span data-stu-id="697f2-p109">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="697f2-149">Lync</span><span class="sxs-lookup"><span data-stu-id="697f2-149">Lync</span></span>
  
```
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="697f2-150">Vous pouvez réactiver le didacticiel en définissant les **données de valeur** sur **1**.</span><span class="sxs-lookup"><span data-stu-id="697f2-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="697f2-151">Comportements du client par défaut</span><span class="sxs-lookup"><span data-stu-id="697f2-151">Default client behaviors</span></span>

<span data-ttu-id="697f2-152">Si votre organisation a deux Skype pour Business Server et Lync Server déployé, l’expérience du client varient en fonction des versions du serveur et l’UI Skype paramètre.</span><span class="sxs-lookup"><span data-stu-id="697f2-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="697f2-153">Le tableau ci-dessous montre l’expérience client initiale en fonction de la version du serveur et du paramètre de l’interface utilisateur :</span><span class="sxs-lookup"><span data-stu-id="697f2-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="697f2-154">**Version du serveur**</span><span class="sxs-lookup"><span data-stu-id="697f2-154">**Server version**</span></span>|<span data-ttu-id="697f2-155">**Paramètre EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="697f2-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="697f2-156">**Expérience client**</span><span class="sxs-lookup"><span data-stu-id="697f2-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="697f2-157">Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="697f2-157">Skype for Business Server</span></span> |<span data-ttu-id="697f2-158">Par défaut</span><span class="sxs-lookup"><span data-stu-id="697f2-158">Default</span></span>  <br/> |<span data-ttu-id="697f2-159">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="697f2-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="697f2-160">Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="697f2-160">Skype for Business Server</span></span>  |<span data-ttu-id="697f2-161">True</span><span class="sxs-lookup"><span data-stu-id="697f2-161">True</span></span>  <br/> |<span data-ttu-id="697f2-162">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="697f2-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="697f2-163">Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="697f2-163">Skype for Business Server</span></span>  |<span data-ttu-id="697f2-164">False</span><span class="sxs-lookup"><span data-stu-id="697f2-164">False</span></span>  <br/> |<span data-ttu-id="697f2-165">Utilisateur invité à passer en mode Lync (l’utilisateur peut opter pour Skype pour les entreprises ultérieurement si vous modifiez le paramètre de l’interface utilisateur sur $true)</span><span class="sxs-lookup"><span data-stu-id="697f2-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="697f2-166">Lync Server 2010 ou Lync Server 2013 (avec les correctifs correctes)</span><span class="sxs-lookup"><span data-stu-id="697f2-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="697f2-167">Par défaut</span><span class="sxs-lookup"><span data-stu-id="697f2-167">Default</span></span>  <br/> |<span data-ttu-id="697f2-168">Utilisateur invité à passer en mode Lync (l’utilisateur peut opter pour Skype pour les entreprises ultérieurement si vous modifiez le paramètre de l’interface utilisateur sur $true)</span><span class="sxs-lookup"><span data-stu-id="697f2-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="697f2-169">Lync Server 2010 ou Lync Server 2013 (avec les correctifs correctes)</span><span class="sxs-lookup"><span data-stu-id="697f2-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="697f2-170">True</span><span class="sxs-lookup"><span data-stu-id="697f2-170">True</span></span>  <br/> |<span data-ttu-id="697f2-171">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="697f2-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="697f2-172">Lync Server 2010 ou Lync Server 2013 (avec les correctifs correctes)</span><span class="sxs-lookup"><span data-stu-id="697f2-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="697f2-173">False</span><span class="sxs-lookup"><span data-stu-id="697f2-173">False</span></span>  <br/> |<span data-ttu-id="697f2-174">Utilisateur invité à passer en mode Lync (l’utilisateur peut opter pour Skype pour les entreprises ultérieurement si vous modifiez le paramètre de l’interface utilisateur sur $true)</span><span class="sxs-lookup"><span data-stu-id="697f2-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="697f2-175">Lync Server 2010 ou Lync Server 2013 (sans correctifs)</span><span class="sxs-lookup"><span data-stu-id="697f2-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="697f2-176">Par défaut</span><span class="sxs-lookup"><span data-stu-id="697f2-176">Default</span></span>  <br/> |<span data-ttu-id="697f2-177">Utilisateur invité à passer en mode Lync (l’utilisateur ne peut pas opter pour Skype pour les entreprises plus tard)</span><span class="sxs-lookup"><span data-stu-id="697f2-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="697f2-178">Le tableau suivant présente l’expérience du client lorsque l’administrateur modifie la valeur initiale de l’expérience Skype UI :</span><span class="sxs-lookup"><span data-stu-id="697f2-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="697f2-179">**Version du serveur**</span><span class="sxs-lookup"><span data-stu-id="697f2-179">**Server version**</span></span>|<span data-ttu-id="697f2-180">**Paramètre EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="697f2-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="697f2-181">**Interface utilisateur du client = Lync**</span><span class="sxs-lookup"><span data-stu-id="697f2-181">**Client UI = Lync**</span></span>|<span data-ttu-id="697f2-182">**UI client = Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="697f2-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="697f2-183">Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="697f2-183">Skype for Business Server</span></span> |<span data-ttu-id="697f2-184">True</span><span class="sxs-lookup"><span data-stu-id="697f2-184">True</span></span>  <br/> |<span data-ttu-id="697f2-185">Utilisateur invité à passer à Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="697f2-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="697f2-186">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="697f2-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="697f2-187">Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="697f2-187">Skype for Business Server</span></span> |<span data-ttu-id="697f2-188">False</span><span class="sxs-lookup"><span data-stu-id="697f2-188">False</span></span>  <br/> |<span data-ttu-id="697f2-189">Mode de Lync</span><span class="sxs-lookup"><span data-stu-id="697f2-189">Lync mode</span></span>  <br/> |<span data-ttu-id="697f2-190">Utilisateur invité à passer en mode de Lync</span><span class="sxs-lookup"><span data-stu-id="697f2-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="697f2-191">Lync Server 2010 ou Lync Server 2013 (avec les correctifs correctes)</span><span class="sxs-lookup"><span data-stu-id="697f2-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="697f2-192">True</span><span class="sxs-lookup"><span data-stu-id="697f2-192">True</span></span>  <br/> |<span data-ttu-id="697f2-193">Utilisateur invité à passer à Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="697f2-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="697f2-194">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="697f2-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="697f2-195">Lync Server 2010 ou Lync Server 2013 (avec les correctifs correctes)</span><span class="sxs-lookup"><span data-stu-id="697f2-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="697f2-196">False</span><span class="sxs-lookup"><span data-stu-id="697f2-196">False</span></span>  <br/> |<span data-ttu-id="697f2-197">Mode de Lync</span><span class="sxs-lookup"><span data-stu-id="697f2-197">Lync mode</span></span>  <br/> |<span data-ttu-id="697f2-198">Utilisateur invité à passer en mode de Lync</span><span class="sxs-lookup"><span data-stu-id="697f2-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="697f2-199">Lync Server 2010 ou Lync Server 2013 (sans correctifs)</span><span class="sxs-lookup"><span data-stu-id="697f2-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="697f2-200">Par défaut</span><span class="sxs-lookup"><span data-stu-id="697f2-200">Default</span></span>  <br/> |<span data-ttu-id="697f2-201">Mode Lync (ne peuvent pas passer à Skype pour les entreprises)</span><span class="sxs-lookup"><span data-stu-id="697f2-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="697f2-202">Mode Lync (ne peuvent pas passer à Skype pour les entreprises)</span><span class="sxs-lookup"><span data-stu-id="697f2-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="697f2-203">Les versions de correctif requises pour gérer la configuration de la Skype pour client d’entreprise sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="697f2-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="697f2-204">Lync Server 2010 - février 2015 mise à jour Cumulative (4.0.7577.710) pour Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="697f2-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="697f2-205">Pour plus d’informations, voir [mises à jour pour Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span><span class="sxs-lookup"><span data-stu-id="697f2-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="697f2-206">Lync Server 2013-2014 décembre mise à jour Cumulative (5.0.8308.857) pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="697f2-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="697f2-207">Pour plus d’informations, voir [mises à jour pour Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span><span class="sxs-lookup"><span data-stu-id="697f2-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="697f2-208">Créer un objet de stratégie de groupe pour modifier le Registre sur un ordinateur joint au domaine</span><span class="sxs-lookup"><span data-stu-id="697f2-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="697f2-209">La mise à jour dans le Registre pour afficher l’expérience du client Lync la première fois qu’un utilisateur lance le Skype pour Business 2015 client doit être effectuée qu’une seule fois.</span><span class="sxs-lookup"><span data-stu-id="697f2-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business 2015 client should be done only once.</span></span> <span data-ttu-id="697f2-210">Si vous utilisez un objet de stratégie de groupe pour mettre à jour le registre, vous devez définir l'objet pour créer une valeur et non mettre à jour les données d'une valeur.</span><span class="sxs-lookup"><span data-stu-id="697f2-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="697f2-211">Lorsque l'objet de stratégie de groupe est appliqué, si la nouvelle valeur n'existe pas, l'objet stratégie de groupe la crée et définit les données de valeur sur 0.</span><span class="sxs-lookup"><span data-stu-id="697f2-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="697f2-212">La procédure suivante décrit comment modifier le Registre afin que l’expérience du client Lync s’affiche la première fois qu’un utilisateur lance le Skype pour client Business 2015.</span><span class="sxs-lookup"><span data-stu-id="697f2-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business 2015 client.</span></span> <span data-ttu-id="697f2-213">Vous pouvez également utiliser cette procédure de mise à jour du registre pour désactiver le didacticiel de l’écran d’accueil comme décrit précédemment.</span><span class="sxs-lookup"><span data-stu-id="697f2-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="697f2-214">Pour créer l’objet GPO</span><span class="sxs-lookup"><span data-stu-id="697f2-214">To create the GPO</span></span>

1. <span data-ttu-id="697f2-215">Démarrez la **Console de gestion des stratégies de groupe**.</span><span class="sxs-lookup"><span data-stu-id="697f2-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="697f2-216">Pour plus d'informations sur l'utilisation de la Console de gestion des stratégies de groupe, reportez-vous à l'article [Console de gestion des stratégies de groupe](https://go.microsoft.com/fwlink/?LinkId=532759).</span><span class="sxs-lookup"><span data-stu-id="697f2-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="697f2-217">Cliquez avec le bouton droit sur le nœud **Objets de stratégie de groupe** et sélectionnez **Nouveau** dans le menu.</span><span class="sxs-lookup"><span data-stu-id="697f2-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="697f2-218">Dans la boîte de dialogue **Nouvel objet GPO**, entrez un nom pour l'objet GPO, par exemple, MakeLyncDefaultUI, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="697f2-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="697f2-219">Cliquez avec le bouton droit sur le nouvel objet GPO que vous venez de créer, puis sélectionnez **Modifier** dans le menu.</span><span class="sxs-lookup"><span data-stu-id="697f2-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="697f2-220">Dans **Éditeur de gestion des stratégies de groupe**, développez **Configuration utilisateur**, **Préférences**, **Paramètres Windows**, puis sélectionnez le nœud **Registre**.</span><span class="sxs-lookup"><span data-stu-id="697f2-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="697f2-221">Cliquez avec le bouton droit sur le nœud **Registre**, puis sélectionnez **Nouveau** > **Élément Registre**.</span><span class="sxs-lookup"><span data-stu-id="697f2-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="697f2-222">Dans la boîte de dialogue **Nouvelles propriétés de registre**, mettez à jour les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="697f2-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="697f2-223">**Champ**</span><span class="sxs-lookup"><span data-stu-id="697f2-223">**Field**</span></span>|<span data-ttu-id="697f2-224">**Valeur à sélectionner ou entrer**</span><span class="sxs-lookup"><span data-stu-id="697f2-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="697f2-225">**Action**</span><span class="sxs-lookup"><span data-stu-id="697f2-225">**Action**</span></span> <br/> |<span data-ttu-id="697f2-226">**Créer**</span><span class="sxs-lookup"><span data-stu-id="697f2-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="697f2-227">**Ruche**</span><span class="sxs-lookup"><span data-stu-id="697f2-227">**Hive**</span></span> <br/> | <span data-ttu-id="697f2-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="697f2-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="697f2-229">**Chemin d’accès à la clé**</span><span class="sxs-lookup"><span data-stu-id="697f2-229">**Key Path**</span></span> <br/> |<span data-ttu-id="697f2-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="697f2-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="697f2-231">**Nom de la valeur**</span><span class="sxs-lookup"><span data-stu-id="697f2-231">**Value name**</span></span> <br/> |<span data-ttu-id="697f2-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="697f2-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="697f2-233">**Type de la valeur**</span><span class="sxs-lookup"><span data-stu-id="697f2-233">**Value type**</span></span> <br/> |<span data-ttu-id="697f2-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="697f2-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="697f2-235">**Données de la valeur**</span><span class="sxs-lookup"><span data-stu-id="697f2-235">**Value data**</span></span> <br/> |<span data-ttu-id="697f2-236">00000000</span><span class="sxs-lookup"><span data-stu-id="697f2-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="697f2-237">Cliquez sur **OK** pour enregistrer les modifications, puis fermez l'objet GPO.</span><span class="sxs-lookup"><span data-stu-id="697f2-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="697f2-238">Ensuite, vous devez lier l’objet GPO créé au groupe d’utilisateurs auquel vous voulez affecter la stratégie, par exemple Unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="697f2-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="697f2-239">Pour utiliser l’objet GPO pour affecter la stratégie</span><span class="sxs-lookup"><span data-stu-id="697f2-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="697f2-240">Dans la Console de gestion des stratégies de groupe, effectuez un clic droit sur l’Unité d’organisation à laquelle vous voulez affecter la stratégie, puis sélectionnez **Lier un objet de stratégie de groupe existant**.</span><span class="sxs-lookup"><span data-stu-id="697f2-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="697f2-241">Dans la boîte de dialogue **Sélectionner un objet GPO**, sélectionnez l'objet GPO créé, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="697f2-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="697f2-242">Sur l'ordinateur de l'utilisateur cible, ouvrez une invite de commandes et tapez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="697f2-242">On the target user's computer, open a command prompt and type the following command:</span></span>
       
```
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. <span data-ttu-id="697f2-243">Dans l'invite de commandes, tapez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="697f2-243">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="697f2-244">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="697f2-244">**gpresult /r**</span></span>
    
    <span data-ttu-id="697f2-245">Vous devriez voir « Objets de stratégie de groupé affectés » avec le nom de l’objet GPO créé s’afficher en-dessous.</span><span class="sxs-lookup"><span data-stu-id="697f2-245">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="697f2-p115">Vous pouvez aussi vérifier que l’objet GPO a correctement mis à jour le Registre sur un ordinateur d’utilisateur en examinant le Registre. Ouvrez l’Éditeur du Registre et accédez à la clé **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**. Si l’objet GPO a correctement mis à jour le Registre, vous verrez une valeur nommée EnableSkypeUI avec une valeur 0.</span><span class="sxs-lookup"><span data-stu-id="697f2-p115">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry. Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key. If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  

