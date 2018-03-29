---
title: Créer des groupes de réponse ou les modifier groupe existant de l’Agent
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
description: Les groupes d’agents définissent les personnes qui peuvent répondre aux appels adressés à un groupe de réponse (appelées « agents »), ainsi que les paramètres qui s’appliquent à tous les agents du groupe.
ms.openlocfilehash: 4ae2869e335bc8d7d8b774f7daf7f5915dcba462
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a><span data-ttu-id="92798-103">Groupes Response Group : création d’un groupe d’agents ou modification d’un groupe d’agents existant</span><span class="sxs-lookup"><span data-stu-id="92798-103">Response Groups: Create New or Edit Existing Agent Group</span></span>
 
<span data-ttu-id="92798-104">Les groupes d’agents définissent les personnes qui peuvent répondre aux appels adressés à un groupe de réponse (appelées « agents »), ainsi que les paramètres qui s’appliquent à tous les agents du groupe.</span><span class="sxs-lookup"><span data-stu-id="92798-104">Agent groups define who can answer calls to a response group (known as agents) and the settings that apply to all the agents in the group.</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="92798-105">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="92798-105">UI Reference</span></span>

<span data-ttu-id="92798-106">La liste ci-dessous décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="92798-106">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="92798-107">**Nom** Chaque groupe d’agents requiert un nom unique.</span><span class="sxs-lookup"><span data-stu-id="92798-107">**Name** Each agent group requires a unique name.</span></span> <span data-ttu-id="92798-108">Utilisez un nom descriptif qui identifie fonction du groupe.</span><span class="sxs-lookup"><span data-stu-id="92798-108">Use a descriptive name that identifies the group's function.</span></span> <span data-ttu-id="92798-109">Par exemple, service d’assistance.</span><span class="sxs-lookup"><span data-stu-id="92798-109">For example, Help Desk.</span></span>
    
- <span data-ttu-id="92798-110">**Description** Ce champ est facultatif.</span><span class="sxs-lookup"><span data-stu-id="92798-110">**Description** This field is optional.</span></span> <span data-ttu-id="92798-111">Elle permet de fournir des détails supplémentaires sur le groupe.</span><span class="sxs-lookup"><span data-stu-id="92798-111">Use it to provide additional details about the group.</span></span>
    
- <span data-ttu-id="92798-112">**Stratégie de participation** Spécifier la façon dont les agents sont à signer, dans le groupe de réponse :</span><span class="sxs-lookup"><span data-stu-id="92798-112">**Participation policy** Specify the way that agents are to sign into the response group:</span></span>
    
  - <span data-ttu-id="92798-p103">Sélectionnez **Informel** pour spécifier que les agents du groupe n’ont pas besoin de se connecter et de se déconnecter. Les agents informels sont connectés automatiquement lorsqu’ils se connectent. Le paramètre par défaut est **Informel**.</span><span class="sxs-lookup"><span data-stu-id="92798-p103">Select **Informal** to specify that the agents in the group do not need to sign in and out. Informal agents are automatically signed in when they sign in. The default is **Informal**.</span></span>
    
  - <span data-ttu-id="92798-115">Sélectionnez **formel** pour spécifier que les agents du groupe doivent se connecter et l’extraction. Lorsque vous sélectionnez cette option, les agents, cliquez sur un élément de menu dans le client pour ouvrir un navigateur et afficher une console de page web pour la connexion et la déconnexion.</span><span class="sxs-lookup"><span data-stu-id="92798-115">Select **Formal** to specify that the agents in the group must sign in and out. When you select this option, agents click a menu item in the client to open a browser and display a web page console for signing in and out.</span></span>
    
- <span data-ttu-id="92798-116">**Heure de l’alerte (secondes)** Spécifier le nombre de secondes à l’anneau d’un agent avant l’appel à l’agent disponible suivant.</span><span class="sxs-lookup"><span data-stu-id="92798-116">**Alert time (seconds)** Specify the number of seconds to ring an agent before offering the call to the next available agent.</span></span> <span data-ttu-id="92798-117">La valeur doit être au moins de 10 secondes et inférieur à 180 secondes.</span><span class="sxs-lookup"><span data-stu-id="92798-117">The value must be at least 10 seconds and less than 180 seconds.</span></span> <span data-ttu-id="92798-118">La valeur par défaut est de 20 secondes.</span><span class="sxs-lookup"><span data-stu-id="92798-118">The default is 20 seconds.</span></span>
    
- <span data-ttu-id="92798-119">**Méthode de routage** Sélectionnez la méthode de détermination de l’ordre dans lequel les agents reçoivent des appels :</span><span class="sxs-lookup"><span data-stu-id="92798-119">**Routing method** Select the method for determining the order in which agents receive calls:</span></span>
    
  - <span data-ttu-id="92798-120">Sélectionnez **Le plus longuement inactif** pour qu’un nouvel appel soit présenté en premier à l’agent qui a été inactif (dont la présence était **Disponible** ou **Inactif(ve)**) le plus longtemps.</span><span class="sxs-lookup"><span data-stu-id="92798-120">Select **Longest idle** to offer a new call first to the agent who has been idle (has had a presence of **Available** or **Inactive**) the longest.</span></span>
    
  - <span data-ttu-id="92798-p105">Sélectionnez **Parallèle** pour qu’un nouvel appel soit présenté à tous les agents disponibles simultanément. L’appel est envoyé au premier agent qui l’accepte.</span><span class="sxs-lookup"><span data-stu-id="92798-p105">Select **Parallel** to offer a new call to all available agents at the same time. The call is sent to the first agent who accepts it.</span></span>
    
  - <span data-ttu-id="92798-123">Sélectionnez **Tourniquet (round robin)** pour qu’un nouvel appel soit présenté à chaque agent, à tour de rôle.</span><span class="sxs-lookup"><span data-stu-id="92798-123">Select **Round robin** to offer a new call to each agent in turn.</span></span>
    
  - <span data-ttu-id="92798-124">Sélectionnez **Série** pour qu’un nouvel appel soit toujours présenté aux agents dans l’ordre dans lequel ils apparaissent dans la liste **Agent**.</span><span class="sxs-lookup"><span data-stu-id="92798-124">Select **Serial** to always offer a new call to agents in the order in which they are listed in the **Agent** list.</span></span>
    
  - <span data-ttu-id="92798-125">Sélectionnez **standard** pour offrir un nouvel appel à tous les agents qui sont connectés et l’application de groupe de réponse en même temps, indépendamment de leur présence en cours.</span><span class="sxs-lookup"><span data-stu-id="92798-125">Select **Attendant** to offer a new call to all agents who are signed in and the Response Group application at the same time, regardless of their current presence.</span></span> <span data-ttu-id="92798-126">Standards et les utilisateurs du client qui sont configurés comme agents peuvent voir tous les appels qui sont en attente et peuvent répondre en attente des appels dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="92798-126">Attendants and client users who are configured as agents can see all the calls that are waiting and can answer waiting calls in any order.</span></span> <span data-ttu-id="92798-127">L’appel est envoyé au premier agent qui l’accepte, et les autres intendants et utilisateurs ne peuvent plus voir l’appel.</span><span class="sxs-lookup"><span data-stu-id="92798-127">The call is sent to the first agent who accepts it, and the other attendants and users no longer see the call.</span></span>
    
- <span data-ttu-id="92798-128">**Agents** Sélectionnez les utilisateurs qui doivent être des agents pour le groupe de réponse dans une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="92798-128">**Agents** Select the users who are to be agents for the response group in one of the following ways:</span></span>
    
  - <span data-ttu-id="92798-129">Sélectionnez l’option **utiliser une liste de distribution de courrier électronique** à utiliser une liste de distribution Exchange.</span><span class="sxs-lookup"><span data-stu-id="92798-129">Select **Use an existing email distribution list** to use an Exchange distribution list.</span></span> <span data-ttu-id="92798-130">Tapez l’adresse de messagerie de la liste de distribution dans **Adresse de la liste de distribution**.</span><span class="sxs-lookup"><span data-stu-id="92798-130">Type the email address of the distribution list in **Distribution list address**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="92798-p108">Vous pouvez sélectionner une seule liste de distribution pour un groupe d’agents. Si la liste de distribution inclut des listes de distribution imbriquées, ces dernières ne sont pas incluses dans le groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="92798-p108">You can select only one distribution list for an agent group. If the distribution list includes nested distribution lists, the nested distribution lists are not included in the agent group.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="92798-133">L’ordre dans lequel les agents sont répertoriés dans la liste de distribution affecte l’ordre dans lequel les agents reçoivent des appels pour le routage en série et de tourniquet.</span><span class="sxs-lookup"><span data-stu-id="92798-133">The order in which agents are listed in the distribution list affects the order in which agents receive calls for round robin and serial routing.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="92798-134">Les membres masqués ou listes masquées risquent d’être visibles pour les administrateurs de groupe de réponse ou des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="92798-134">Hidden memberships or hidden lists might become visible to Response Group administrators or users.</span></span> <span data-ttu-id="92798-135">Pour plus d’informations, consultez [créer ou modifier un groupe d’agent dans Skype pour 2015 de Business](../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span><span class="sxs-lookup"><span data-stu-id="92798-135">For details, see [Create or modify an agent group in Skype for Business 2015](../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span></span> 
  
  - <span data-ttu-id="92798-p110">Sélectionnez **Définir un groupe personnalisé d’agents** pour sélectionner les utilisateurs à affecter comme agents pour le groupe de réponse. Cliquez sur **Sélectionner** pour ajouter un agent à la liste. Cliquez sur **Supprimer** pour supprimer un agent sélectionné de la liste.</span><span class="sxs-lookup"><span data-stu-id="92798-p110">Select **Define a custom group of agents** to select the users you want to assign as agents for the response group. Click **Select** to add an agent to the list. Click **Remove** to delete a selected agent from the list.</span></span>
    
    <span data-ttu-id="92798-p111">Les flèches Haut et Bas déplacent un agent sélectionné vers le haut ou vers le bas dans la liste des agents. L’ordre des agents dans la liste affecte l’ordre dans lequel les agents reçoivent des appels pour le routage en série et de tourniquet.</span><span class="sxs-lookup"><span data-stu-id="92798-p111">The up and down arrows move a selected agent up and down in the agent list. The order of agents in the list affects the order in which agents receive calls for round robin and serial routing.</span></span>
    
<span data-ttu-id="92798-141">Pour plus d’informations sur les fonctionnalités de groupe de la réponse de, afficher un [Plan pour l’application de groupe de réponse dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="92798-141">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="92798-142">Pour plus d’informations sur l’utilisation de groupes d’agents, consultez [Gestion des groupes de l’Agent](http://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) dans la documentation sur les opérations.</span><span class="sxs-lookup"><span data-stu-id="92798-142">For details about working with agent groups, see [Managing Agent Groups](http://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>
  

