---
title: Configurer la réunion page jointure dans Skype pour Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Résumé : Apprenez à configurer la réunion page jointure dans Skype pour Business Server 2015.'
ms.openlocfilehash: c0b3ed39fc2f7a1a48635353cc1db673a4bd1cd5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server-2015"></a><span data-ttu-id="cb853-103">Configurer la réunion page jointure dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cb853-103">Configure the meeting join page in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cb853-104">**Résumé :** Apprenez à configurer la réunion page jointure dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="cb853-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="cb853-105">Lorsqu’un utilisateur clique sur un lien d’une réunion dans une demande de réunion, la réunion page de jointure détecte si un Skype pour client d’entreprise est déjà installé sur l’ordinateur de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cb853-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="cb853-106">Si un client est déjà installé, le client ouvre et rejoint la réunion.</span><span class="sxs-lookup"><span data-stu-id="cb853-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="cb853-107">Si un client n’est pas installé, par défaut la 2015 version de Skype pour client d’entreprise s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="cb853-107">If a client is not installed, by default the 2015 version of Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="cb853-108">Configurer la réunion page d’inscription</span><span class="sxs-lookup"><span data-stu-id="cb853-108">Configure the meeting join page</span></span>

<span data-ttu-id="cb853-109">Vous pouvez modifier le comportement de la jointure de réunion si vous souhaitez permettre aux utilisateurs de participer à des conférences avec d’autres versions du client de la page.</span><span class="sxs-lookup"><span data-stu-id="cb853-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="cb853-110">Ces options de configuration ont été retirées du Skype pour Business Server du Panneau de configuration, mais vous les configurez à l’aide de l’applet de commande Set-CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="cb853-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="cb853-111">**Paramètres de Page joindre ensemble-CsWebServiceConfiguration de réunion**</span><span class="sxs-lookup"><span data-stu-id="cb853-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="cb853-112">**Paramètre de CsWebServiceConfiguration de l’ensemble**</span><span class="sxs-lookup"><span data-stu-id="cb853-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="cb853-113">**Description**</span><span class="sxs-lookup"><span data-stu-id="cb853-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cb853-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="cb853-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="cb853-115">Ce paramètre a été désapprouvé à utiliser avec la version locale de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="cb853-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server 2015.</span></span>  <br/> <span data-ttu-id="cb853-116">Si la valeur True, les utilisateurs se joindre à une réunion à l’aide d’une application client autre que Skype pour entreprise auront la possibilité de joindre la réunion à l’aide de l’application client en cours.</span><span class="sxs-lookup"><span data-stu-id="cb853-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="cb853-117">La valeur par défaut est False.</span><span class="sxs-lookup"><span data-stu-id="cb853-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="cb853-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="cb853-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="cb853-119">Ce paramètre a été désapprouvé à utiliser avec la version locale de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="cb853-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server 2015.</span></span>  <br/>  <span data-ttu-id="cb853-120">Si la valeur True, autres options pour rejoindre une conférence en ligne sont automatiquement développées et aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="cb853-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="cb853-121">Si la valeur False (valeur par défaut), ces options seront disponibles, mais l’utilisateur aura afficher la liste des options pour eux-mêmes.</span><span class="sxs-lookup"><span data-stu-id="cb853-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

