---
title: Configuration de la page de participation à une réunion dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Résumé : Découvrez comment configurer la page de participation à une réunion dans Skype entreprise Server.'
ms.openlocfilehash: 7381db4983b5a2c1ec6dccf474f0b381e079e222
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818515"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="d4647-103">Configuration de la page de participation à une réunion dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="d4647-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="d4647-104">**Résumé :** En savoir plus sur la configuration de la page de participation à une réunion dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d4647-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="d4647-105">Lorsqu’un utilisateur clique sur un lien de réunion dans une demande de réunion, la page de participation à la réunion détecte si un client Skype entreprise est déjà installé sur l’ordinateur de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d4647-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="d4647-106">Si un client est déjà installé, le client ouvre et joint la réunion.</span><span class="sxs-lookup"><span data-stu-id="d4647-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="d4647-107">Si un client n’est pas installé, le client Skype entreprise s’ouvre par défaut.</span><span class="sxs-lookup"><span data-stu-id="d4647-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="d4647-108">Configuration de la page de participation à une réunion</span><span class="sxs-lookup"><span data-stu-id="d4647-108">Configure the meeting join page</span></span>

<span data-ttu-id="d4647-109">Vous pouvez modifier le comportement de la page de participation à une réunion si vous voulez permettre aux utilisateurs de participer à des réunions avec d’autres versions du client.</span><span class="sxs-lookup"><span data-stu-id="d4647-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="d4647-110">Ces options de configuration ont été supprimées du panneau de configuration Skype entreprise Server, mais vous les configurez à l’aide de l’applet de commande Set-CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d4647-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="d4647-111">**Ensemble de pages de participation à une réunion-paramètres de CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="d4647-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="d4647-112">**Paramètre SET-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="d4647-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="d4647-113">**Description**</span><span class="sxs-lookup"><span data-stu-id="d4647-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4647-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="d4647-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="d4647-115">Ce paramètre a été déconseillé pour une utilisation avec la version locale de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d4647-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="d4647-116">Si elle est définie sur true, les utilisateurs qui rejoignent une réunion à l’aide d’une application client autre que Skype entreprise seront en mesure de rejoindre la réunion à l’aide de leur application client actuelle.</span><span class="sxs-lookup"><span data-stu-id="d4647-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="d4647-117">La valeur par défaut est False.</span><span class="sxs-lookup"><span data-stu-id="d4647-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="d4647-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="d4647-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="d4647-119">Ce paramètre a été déconseillé pour une utilisation avec la version locale de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d4647-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="d4647-120">Si elle a la valeur true, d’autres options de participation à une conférence en ligne sont automatiquement développées et affichées aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d4647-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="d4647-121">Si elle a la valeur false (valeur par défaut), les options suivantes sont disponibles, mais l’utilisateur doit afficher la liste des options pour eux-mêmes.</span><span class="sxs-lookup"><span data-stu-id="d4647-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

