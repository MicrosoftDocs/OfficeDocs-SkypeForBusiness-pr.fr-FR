---
title: Configuration de la page de participation à une réunion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Lorsqu’un utilisateur clique sur un lien de réunion dans une demande de réunion, la page de participation à une réunion détecte le client déjà installé sur l’ordinateur de l’utilisateur. Si un client est déjà installé, ce client ouvre et joint la réunion. Si un client n’est pas installé, l’application Web s’ouvre par défaut.
ms.openlocfilehash: 35b8b816d5c01f3061dc697cf7f37a4314a5f083
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813792"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="cbc12-105">Configuration de la page de participation à une réunion</span><span class="sxs-lookup"><span data-stu-id="cbc12-105">Configure the meeting join page</span></span>

<span data-ttu-id="cbc12-106">Lorsqu’un utilisateur clique sur un lien de réunion dans une demande de réunion, la page de participation à une réunion détecte le client déjà installé sur l’ordinateur de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cbc12-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="cbc12-107">Si un client est déjà installé, ce client ouvre et joint la réunion.</span><span class="sxs-lookup"><span data-stu-id="cbc12-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="cbc12-108">Si un client n’est pas installé, l’application Web s’ouvre par défaut.</span><span class="sxs-lookup"><span data-stu-id="cbc12-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="cbc12-109">Vous pouvez modifier le comportement de la page de participation à une réunion si vous voulez permettre aux utilisateurs de participer à des réunions.</span><span class="sxs-lookup"><span data-stu-id="cbc12-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="cbc12-110">Ces options de configuration ont été supprimées du panneau de configuration, mais vous les configurez à l’aide de l’applet de commande CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="cbc12-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="cbc12-111">**Paramètres d’CsWebServiceConfiguration de la page de participation à une réunion**</span><span class="sxs-lookup"><span data-stu-id="cbc12-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="cbc12-112">**Paramètre CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="cbc12-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="cbc12-113">**Description**</span><span class="sxs-lookup"><span data-stu-id="cbc12-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cbc12-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="cbc12-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="cbc12-115">S’il est défini sur true, les utilisateurs qui rejoignent une réunion à l’aide d’une application client autre que Lync seront en mesure de rejoindre la réunion.</span><span class="sxs-lookup"><span data-stu-id="cbc12-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="cbc12-116">La valeur par défaut est False.</span><span class="sxs-lookup"><span data-stu-id="cbc12-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="cbc12-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="cbc12-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="cbc12-118">Lorsque cette propriété est définie sur true, d’autres options permettant de participer à une conférence en ligne sont automatiquement développées et affichées aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="cbc12-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="cbc12-119">Lorsque ce paramètre est défini sur false (valeur par défaut), les options suivantes sont disponibles, mais l’utilisateur doit afficher la liste des options pour eux-mêmes.</span><span class="sxs-lookup"><span data-stu-id="cbc12-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="cbc12-120">Pour configurer la page de participation à une réunion à l’aide de Skype entreprise Server 2019 Management Shell</span><span class="sxs-lookup"><span data-stu-id="cbc12-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="cbc12-121">Démarrez Skype entreprise Server 2019 Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Microsoft Skype entreprise Server 2019**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="cbc12-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="cbc12-122">Exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="cbc12-122">Run the following cmdlet:</span></span> 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="cbc12-123">Ce cmdlet renvoie les paramètres de configuration de service Web.</span><span class="sxs-lookup"><span data-stu-id="cbc12-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="cbc12-124">Exécutez la commande suivante, avec les paramètres définis sur true ou false, en fonction de votre préférence (pour plus d’informations sur les paramètres de cette applet de commande, reportez-vous à la documentation de [Skype entreprise Server Management Shell](../../SfbServer/manage/management-shell.md) ) :</span><span class="sxs-lookup"><span data-stu-id="cbc12-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


