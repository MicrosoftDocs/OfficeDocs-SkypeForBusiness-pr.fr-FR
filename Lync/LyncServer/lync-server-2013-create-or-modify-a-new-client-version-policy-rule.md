---
title: 'Lync Server 2013 : création ou modification d’une règle de stratégie de version de client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 442341c51ef6477f72fb9e88cdea5fe7fc527aa8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="df932-102">Créer ou modifier une règle de stratégie de nouvelle version du client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df932-102">Create or modify a new client version policy rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df932-103">_**Dernière modification de la rubrique :** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="df932-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="df932-104">Les règles de stratégie de version du client définissent les actions qui doivent être effectuées lorsque les utilisateurs essaient de se connecter à l’aide de clients et de versions client spécifiques.</span><span class="sxs-lookup"><span data-stu-id="df932-104">Client version policy rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="df932-105">Vous pouvez créer ou modifier des règles individuelles pour une stratégie de version de client à partir du panneau de configuration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df932-105">You can create or modify individual rules for a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="df932-106">Les règles sont classées par ordre de priorité.</span><span class="sxs-lookup"><span data-stu-id="df932-106">Rules are listed in order of precedence.</span></span> <span data-ttu-id="df932-107">Par exemple, si vous avez une règle qui permet aux clients exécutant la version 1,5 de se connecter, suivi par une règle qui empêche les clients exécutant une version antérieure à 2,0, la première règle est prioritaire et les clients exécutant la version 1,5 sont autorisés à se connecter.</span><span class="sxs-lookup"><span data-stu-id="df932-107">For example, if you have a rule that allows clients running version 1.5 to connect, followed by a rule that blocks clients running a version earlier than 2.0, the first rule takes precedence, and clients running version 1.5 are allowed to connect.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="df932-108">Pour créer ou modifier des règles de stratégie de version de client avec le panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="df932-108">To create or modify client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="df932-109">[Créez ou modifiez une nouvelle stratégie de version de client dans Lync server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) avec le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="df932-109">[Create or modify a new client version policy in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) with Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="df932-110">Dans la page **modifier la stratégie de version du client** , effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="df932-110">On the **Edit Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="df932-111">Cliquez sur **nouveau** pour créer une règle de version de client.</span><span class="sxs-lookup"><span data-stu-id="df932-111">Click **New** to create a new client version rule.</span></span>
    
      - <span data-ttu-id="df932-112">Cliquez sur l’un des types de clients définis dans la liste, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="df932-112">Click one of the defined client types in the list, and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="df932-113">Vous pouvez utiliser des caractères génériques pour indiquer le type de client.</span><span class="sxs-lookup"><span data-stu-id="df932-113">You can use wildcards to indicate the client type.</span></span>

    
    </div>

3.  <span data-ttu-id="df932-114">Dans **agent utilisateur**, sélectionnez un type de client.</span><span class="sxs-lookup"><span data-stu-id="df932-114">In **User agent**, select a client type.</span></span>

4.  <span data-ttu-id="df932-115">Sous **numéro de version**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="df932-115">Under **Version number**, do the following:</span></span>
    
      - <span data-ttu-id="df932-116">Dans **version principale**, tapez le numéro qui correspond à la version majeure du client.</span><span class="sxs-lookup"><span data-stu-id="df932-116">In **Major version**, type the number that corresponds to the major release of the client.</span></span>
    
      - <span data-ttu-id="df932-117">Dans **version mineure**, tapez le numéro qui correspond à la version mineure du client.</span><span class="sxs-lookup"><span data-stu-id="df932-117">In **Minor version**, type the number that corresponds to the minor release of the client.</span></span>
    
      - <span data-ttu-id="df932-118">Dans **générer**, tapez le numéro qui correspond à la version majeure et mineure du client.</span><span class="sxs-lookup"><span data-stu-id="df932-118">In **Build**, type the number that corresponds to the major and minor release of the client.</span></span>
    
      - <span data-ttu-id="df932-119">Dans **mise à jour**, tapez le numéro qui correspond à la version mise à jour du client.</span><span class="sxs-lookup"><span data-stu-id="df932-119">In **Update**, type the number that corresponds to the updated release of the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="df932-120">Vous pouvez utiliser des caractères génériques pour indiquer le numéro de version du client.</span><span class="sxs-lookup"><span data-stu-id="df932-120">You can use wildcards to indicate the client version number.</span></span>

    
    </div>

5.  <span data-ttu-id="df932-121">Pour spécifier l’opération correspondante pour la version du client spécifiée dans les étapes précédentes, dans **opération de comparaison**, cliquez sur l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="df932-121">To specify the matching operation for the client version you specified in the preceding steps, in **Comparison operation**, click one of the following:</span></span>
    
      - <span data-ttu-id="df932-122">**Identique à**</span><span class="sxs-lookup"><span data-stu-id="df932-122">**Same as**</span></span>
    
      - <span data-ttu-id="df932-123">**Différent de**</span><span class="sxs-lookup"><span data-stu-id="df932-123">**Is not**</span></span>
    
      - <span data-ttu-id="df932-124">**Antérieur à**</span><span class="sxs-lookup"><span data-stu-id="df932-124">**Newer than**</span></span>
    
      - <span data-ttu-id="df932-125">**Antérieur ou simultané**</span><span class="sxs-lookup"><span data-stu-id="df932-125">**Newer than or same as**</span></span>
    
      - <span data-ttu-id="df932-126">**Postérieur à**</span><span class="sxs-lookup"><span data-stu-id="df932-126">**Older than**</span></span>
    
      - <span data-ttu-id="df932-127">**Postérieur ou simultané**</span><span class="sxs-lookup"><span data-stu-id="df932-127">**Older than or same as**</span></span>

6.  <span data-ttu-id="df932-128">Pour spécifier l’action à exécuter lorsque les critères spécifiés dans les étapes précédentes sont remplis, **cliquez sur l'** une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="df932-128">To specify the action to perform when the criteria in the preceding steps are met, click one of the following in **Action**:</span></span>
    
      - <span data-ttu-id="df932-129">Pour permettre au client de se connecter, cliquez sur **autoriser**.</span><span class="sxs-lookup"><span data-stu-id="df932-129">To allow the client to log on, click **Allow**.</span></span>
    
      - <span data-ttu-id="df932-130">Pour permettre au client de se connecter et de recevoir des mises à jour de Windows Server Update service ou de Microsoft Update, cliquez sur **autoriser et mettre à niveau**.</span><span class="sxs-lookup"><span data-stu-id="df932-130">To allow the client to log on and receive updates from Windows Server Update Service or Microsoft Update, click **Allow and Upgrade**.</span></span> <span data-ttu-id="df932-131">Cette action est disponible uniquement en cas de sélection de l’agent utilisateur **OC** .</span><span class="sxs-lookup"><span data-stu-id="df932-131">This action is available only when user agent **OC** is selected.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="df932-132">La sélection de cette action entraîne l’affichage d’une notification lors de la prochaine connexion de l’utilisateur à Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="df932-132">Selecting this action causes a notification to appear the next time users sign in to Lync 2013.</span></span> <span data-ttu-id="df932-133">La notification indique qu’une mise à jour est disponible, même si des mises à jour n’ont pas encore été publiées dans Windows Server Update service ou Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="df932-133">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="df932-134">Pour éviter toute confusion, ne sélectionnez cette action qu’après que les mises à jour sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="df932-134">To avoid confusion, you should choose this action only after updates become available.</span></span>

        
        </div>
    
      - <span data-ttu-id="df932-135">Pour permettre au client de se connecter et d’afficher un message concernant l’emplacement de téléchargement d’une autre version du client, cliquez sur **autoriser avec une URL**.</span><span class="sxs-lookup"><span data-stu-id="df932-135">To allow the client to log on and display a message about where to download another client version, click **Allow with URL**.</span></span> <span data-ttu-id="df932-136">Vous spécifiez l’URL plus loin dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="df932-136">You specify the URL later in this procedure.</span></span>
    
      - <span data-ttu-id="df932-137">Pour empêcher le client de se connecter, cliquez sur **bloquer**.</span><span class="sxs-lookup"><span data-stu-id="df932-137">To prevent the client from logging on, click **Block**.</span></span>
    
      - <span data-ttu-id="df932-138">Pour empêcher le client de se connecter et de permettre au client de recevoir des mises à jour de Windows Server Update service ou Microsoft Update, cliquez sur **bloquer et mettre à niveau**.</span><span class="sxs-lookup"><span data-stu-id="df932-138">To prevent the client from logging on and allow the client to receive updates from Windows Server Update Service or Microsoft Update, click **Block and Upgrade**.</span></span> <span data-ttu-id="df932-139">Cette action est disponible uniquement en cas de sélection de l’agent utilisateur **OC** .</span><span class="sxs-lookup"><span data-stu-id="df932-139">This action is available only when user agent **OC** is selected.</span></span>
    
      - <span data-ttu-id="df932-140">Pour empêcher le client de se connecter et d’afficher un message concernant l’emplacement de téléchargement d’une autre version du client, cliquez sur **bloquer avec l’URL**.</span><span class="sxs-lookup"><span data-stu-id="df932-140">To prevent the client from logging on and display a message about where to download another client version, click **Block with URL**.</span></span> <span data-ttu-id="df932-141">Vous spécifiez l’URL plus loin dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="df932-141">You specify the URL later in this procedure.</span></span>

7.  <span data-ttu-id="df932-142">Facultatif Si vous avez cliqué sur **autoriser avec** l’URL ou **bloquer avec l’URL** lors de l’étape précédente, tapez l’URL de téléchargement du client à inclure dans le message dans l' **URL**.</span><span class="sxs-lookup"><span data-stu-id="df932-142">(Optional) If you clicked **Allow with URL** or **Block with URL** in the previous step, type the client download URL to include in the message in **URL**.</span></span>

8.  <span data-ttu-id="df932-143">Cliquez sur **OK**, puis sur **valider**.</span><span class="sxs-lookup"><span data-stu-id="df932-143">Click **OK**, and then click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

