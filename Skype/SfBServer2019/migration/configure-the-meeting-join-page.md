---
title: Configuration de la page de participation à une réunion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: End User
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Lorsqu’un utilisateur clique sur un lien de la réunion dans une demande de réunion, la réunion page de participation aux détecte que le client est déjà installé sur l’ordinateur de l’utilisateur. Si un client est déjà installé, que le client s’ouvre et rejoint la réunion. Si un client n’est pas installé, par défaut l’application Web s’ouvre.
ms.openlocfilehash: 88ae915318505efef6ae716a17217aaa1e7b12df
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238715"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="9a7f3-105">Configuration de la page de participation à une réunion</span><span class="sxs-lookup"><span data-stu-id="9a7f3-105">Configure the meeting join page</span></span>

<span data-ttu-id="9a7f3-106">Lorsqu’un utilisateur clique sur un lien de la réunion dans une demande de réunion, la réunion page de participation aux détecte que le client est déjà installé sur l’ordinateur de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9a7f3-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="9a7f3-107">Si un client est déjà installé, que le client s’ouvre et rejoint la réunion.</span><span class="sxs-lookup"><span data-stu-id="9a7f3-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="9a7f3-108">Si un client n’est pas installé, par défaut l’application Web s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="9a7f3-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="9a7f3-109">Vous pouvez modifier le comportement de la participation aux réunions de page si vous souhaitez autoriser les utilisateurs à participer à des réunions.</span><span class="sxs-lookup"><span data-stu-id="9a7f3-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="9a7f3-110">Ces options de configuration ont été supprimées dans le panneau de configuration, mais les configurer à l’aide de l’applet de commande CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9a7f3-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="9a7f3-111">**Paramètres CsWebServiceConfiguration de la Page de participation aux réunions**</span><span class="sxs-lookup"><span data-stu-id="9a7f3-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="9a7f3-112">**Paramètre CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="9a7f3-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="9a7f3-113">**Description**</span><span class="sxs-lookup"><span data-stu-id="9a7f3-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9a7f3-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="9a7f3-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="9a7f3-115">Si défini sur True, les utilisateurs qui rejoignent une réunion à l’aide d’une application cliente autre que Lync aura la possibilité de participer à la réunion.</span><span class="sxs-lookup"><span data-stu-id="9a7f3-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="9a7f3-116">La valeur par défaut est False.</span><span class="sxs-lookup"><span data-stu-id="9a7f3-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="9a7f3-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="9a7f3-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="9a7f3-118">Lorsque la valeur True, les options de substitution pour la participation à une conférence en ligne sera automatiquement développée et affichée aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="9a7f3-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="9a7f3-119">Lorsque la valeur False (valeur par défaut), ces options seront disponibles, mais l’utilisateur aura afficher la liste des options pour eux-mêmes.</span><span class="sxs-lookup"><span data-stu-id="9a7f3-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="9a7f3-120">Pour configurer la réunion page d’inscription à l’aide de Skype pour Business Server 2019 Management Shell</span><span class="sxs-lookup"><span data-stu-id="9a7f3-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="9a7f3-121">Démarrez le Skype pour Business Server 2019 Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Microsoft Skype pour Business Server 2019**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9a7f3-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="9a7f3-122">Exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9a7f3-122">Run the following cmdlet:</span></span> 
    
   ```
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="9a7f3-123">Cette applet de commande renvoie le site web de paramètres de configuration de service.</span><span class="sxs-lookup"><span data-stu-id="9a7f3-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="9a7f3-124">Exécutez la commande suivante, avec les paramètres dont la valeur est True ou False selon votre préférence (pour plus d’informations sur les paramètres de cette applet de commande, voir la documentation de [Skype pour Business Server Management Shell](../../SfbServer/manage/management-shell.md) ) :</span><span class="sxs-lookup"><span data-stu-id="9a7f3-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


