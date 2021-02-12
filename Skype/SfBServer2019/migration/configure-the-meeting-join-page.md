---
title: Configuration de la page de participation à une réunion
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Lorsqu’un utilisateur clique sur un lien de réunion dans une demande de réunion, la page de réunion détecte le client déjà installé sur l’ordinateur de l’utilisateur. Si c’est le cas, ce client s’ouvre et se joint à la réunion. Si un client n’est pas installé, l’application Web s’ouvre par défaut.
ms.openlocfilehash: a7bb0983438708bbc0d30cd527eb494491c3cbf2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754024"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="07b1b-105">Configuration de la page de participation à une réunion</span><span class="sxs-lookup"><span data-stu-id="07b1b-105">Configure the meeting join page</span></span>

<span data-ttu-id="07b1b-106">Lorsqu’un utilisateur clique sur un lien de réunion dans une demande de réunion, la page de réunion détecte le client déjà installé sur l’ordinateur de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="07b1b-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="07b1b-107">Si c’est le cas, ce client s’ouvre et se joint à la réunion.</span><span class="sxs-lookup"><span data-stu-id="07b1b-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="07b1b-108">Si un client n’est pas installé, l’application Web s’ouvre par défaut.</span><span class="sxs-lookup"><span data-stu-id="07b1b-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="07b1b-109">Vous pouvez modifier le comportement de la page de réunion si vous souhaitez autoriser les utilisateurs à participer à des réunions.</span><span class="sxs-lookup"><span data-stu-id="07b1b-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="07b1b-110">Ces options de configuration ont été supprimées du Panneau de configuration, mais vous les configurez à l’aide de l’cmdlet CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="07b1b-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="07b1b-111">**Paramètres CsWebServiceConfiguration de la page de participation aux réunions**</span><span class="sxs-lookup"><span data-stu-id="07b1b-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="07b1b-112">**Paramètre CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="07b1b-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="07b1b-113">**Description**</span><span class="sxs-lookup"><span data-stu-id="07b1b-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="07b1b-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="07b1b-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="07b1b-115">Si la valeur est True, les utilisateurs qui rejoignent une réunion à l’aide d’une application cliente autre que Lync auront la possibilité de participer à la réunion.</span><span class="sxs-lookup"><span data-stu-id="07b1b-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="07b1b-116">La valeur par défaut est False.</span><span class="sxs-lookup"><span data-stu-id="07b1b-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="07b1b-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="07b1b-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="07b1b-118">Si la valeur est True, les autres options de rejoindre une conférence en ligne sont automatiquement étendues et affichées aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="07b1b-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="07b1b-119">Si la valeur est False (valeur par défaut), ces options seront disponibles, mais l’utilisateur devra afficher la liste des options pour lui-même.</span><span class="sxs-lookup"><span data-stu-id="07b1b-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="07b1b-120">Pour configurer la page de réunion à l’aide de Skype Entreprise Server 2019 Management Shell</span><span class="sxs-lookup"><span data-stu-id="07b1b-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="07b1b-121">Démarrez Skype Entreprise Server 2019 Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Microsoft Skype Entreprise **Server 2019,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="07b1b-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="07b1b-122">Exécutez la cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="07b1b-122">Run the following cmdlet:</span></span> 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="07b1b-123">Cette applet de commande renvoie les paramètres de configuration du service Web.</span><span class="sxs-lookup"><span data-stu-id="07b1b-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="07b1b-124">Exécutez la commande suivante, avec les paramètres définies sur True ou False, en fonction de vos préférences (pour plus d’informations sur les paramètres de cette cmdlet, voir la documentation de [Skype Entreprise Server Management Shell)](../../SfbServer/manage/management-shell.md) :</span><span class="sxs-lookup"><span data-stu-id="07b1b-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


