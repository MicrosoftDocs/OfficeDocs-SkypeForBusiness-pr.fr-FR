---
title: Configurer la page de réunion dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Résumé : Découvrez comment configurer la page de réunion dans Skype Entreprise Server.'
ms.openlocfilehash: 247664a3ff4bbc4ee055775d26f1d077b662752b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828034"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="c7adf-103">Configurer la page de réunion dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="c7adf-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="c7adf-104">**Résumé :** Découvrez comment configurer la page de rejoindre une réunion dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c7adf-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="c7adf-105">Lorsqu’un utilisateur clique sur un lien de réunion dans une demande de réunion, la page de réunion détecte si un client Skype Entreprise est déjà installé sur l’ordinateur de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c7adf-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="c7adf-106">Si c’est le cas, ce client s’ouvre et se joint à la réunion.</span><span class="sxs-lookup"><span data-stu-id="c7adf-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="c7adf-107">Si un client n’est pas installé, le client Skype Entreprise s’ouvre par défaut.</span><span class="sxs-lookup"><span data-stu-id="c7adf-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="c7adf-108">Configuration de la page de participation à une réunion</span><span class="sxs-lookup"><span data-stu-id="c7adf-108">Configure the meeting join page</span></span>

<span data-ttu-id="c7adf-109">Vous pouvez modifier le comportement de la page de rejoindre la réunion si vous souhaitez autoriser les utilisateurs à participer à des réunions avec d’autres versions du client.</span><span class="sxs-lookup"><span data-stu-id="c7adf-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="c7adf-110">Ces options de configuration ont été supprimées du Panneau de configuration de Skype Entreprise Server, mais vous les configurez à l’aide de lSet-CsWebServiceConfiguration de commande.</span><span class="sxs-lookup"><span data-stu-id="c7adf-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="c7adf-111">**Paramètres de la page de Set-CsWebServiceConfiguration réunion**</span><span class="sxs-lookup"><span data-stu-id="c7adf-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="c7adf-112">**Paramètre Set-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="c7adf-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="c7adf-113">**Description**</span><span class="sxs-lookup"><span data-stu-id="c7adf-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c7adf-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="c7adf-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="c7adf-115">Ce paramètre a été supprimé pour une utilisation avec la version sur site de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c7adf-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="c7adf-116">Si la valeur est True, les utilisateurs qui rejoignent une réunion à l’aide d’une application cliente autre que Skype Entreprise auront la possibilité de participer à la réunion à l’aide de leur application cliente actuelle.</span><span class="sxs-lookup"><span data-stu-id="c7adf-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="c7adf-117">La valeur par défaut est False.</span><span class="sxs-lookup"><span data-stu-id="c7adf-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="c7adf-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="c7adf-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="c7adf-119">Ce paramètre a été supprimé pour une utilisation avec la version sur site de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c7adf-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="c7adf-120">Si la valeur est True, les autres options de rejoindre une conférence en ligne sont automatiquement étendues et affichées aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c7adf-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="c7adf-121">Si la valeur est False (valeur par défaut), ces options seront disponibles, mais l’utilisateur devra afficher la liste des options pour lui-même.</span><span class="sxs-lookup"><span data-stu-id="c7adf-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

