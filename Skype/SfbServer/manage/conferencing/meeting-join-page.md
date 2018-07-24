---
title: Configurer la réunion page de participation dans Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Résumé : Découvrez comment configurer la réunion page de participation dans Skype pour Business Server.'
ms.openlocfilehash: 7574dee341e0226a6a6e2ee8c77cdfb2353beb5a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20977613"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="20c77-103">Configurer la réunion page de participation dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="20c77-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="20c77-104">**Résumé :** Découvrez comment configurer la réunion page de participation dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="20c77-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="20c77-105">Lorsqu’un utilisateur clique sur un lien de la réunion dans une demande de réunion, la réunion page de participation aux détecte si un Skype pour client d’entreprise est déjà installé sur l’ordinateur de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="20c77-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="20c77-106">Si un client est déjà installé, le client s’ouvre et rejoint la réunion.</span><span class="sxs-lookup"><span data-stu-id="20c77-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="20c77-107">Si un client n’est pas installé, par défaut le Skype pour les entreprises client s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="20c77-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="20c77-108">Configurer la réunion page de participation aux</span><span class="sxs-lookup"><span data-stu-id="20c77-108">Configure the meeting join page</span></span>

<span data-ttu-id="20c77-109">Vous pouvez modifier le comportement de la participation aux réunions de page si vous souhaitez autoriser les utilisateurs à participer à des réunions avec d’autres versions du client.</span><span class="sxs-lookup"><span data-stu-id="20c77-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="20c77-110">Ces options de configuration ont été supprimées de la Skype pour le panneau de configuration serveur Business, mais les configurer à l’aide de l’applet de commande Set-CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="20c77-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="20c77-111">**Paramètres de participer à Set-CsWebServiceConfiguration de la Page de réunion**</span><span class="sxs-lookup"><span data-stu-id="20c77-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="20c77-112">**Paramètre SET-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="20c77-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="20c77-113">**Description**</span><span class="sxs-lookup"><span data-stu-id="20c77-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="20c77-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="20c77-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="20c77-115">Ce paramètre est déconseillé pour une utilisation avec la version locale de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="20c77-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="20c77-116">Si la valeur True, les utilisateurs à une réunion à l’aide d’une application cliente autre que Skype pour les entreprises auront la possibilité de participer à la réunion à l’aide de l’application cliente en cours.</span><span class="sxs-lookup"><span data-stu-id="20c77-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="20c77-117">La valeur par défaut est False.</span><span class="sxs-lookup"><span data-stu-id="20c77-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="20c77-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="20c77-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="20c77-119">Ce paramètre est déconseillé pour une utilisation avec la version locale de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="20c77-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="20c77-120">Si défini sur True, autres options pour participer à une conférence en ligne sont automatiquement développé et affichée aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="20c77-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="20c77-121">Si la valeur False (valeur par défaut), ces options seront disponibles, mais l’utilisateur aura afficher la liste des options pour eux-mêmes.</span><span class="sxs-lookup"><span data-stu-id="20c77-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

