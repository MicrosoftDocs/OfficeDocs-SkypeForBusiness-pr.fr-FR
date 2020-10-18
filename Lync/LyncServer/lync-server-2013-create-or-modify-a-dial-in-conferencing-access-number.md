---
title: 'Lync Server 2013 : création ou modification d’un numéro d’accès à une conférence rendez-vous'
description: 'Lync Server 2013 : création ou modification d’un numéro d’accès à une conférence rendez-vous.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 187361ab839fe2f80fda7cb68285c8f36398f5a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577960"
---
# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="66d8f-103">Création ou modification d’un numéro d’accès à une conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66d8f-103">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66d8f-104">_**Dernière modification de la rubrique :** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="66d8f-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="66d8f-105">Procédez comme suit pour créer ou modifier un numéro d’accès à une conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="66d8f-105">Follow these steps if you want to create or modify a dial-in conferencing access number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="66d8f-106">Avant de créer un numéro d’accès entrant, vous devez définir une région de conférence rendez-vous dans le plan de numérotation associé au nouveau numéro d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="66d8f-106">Before you create a new dial-in access number, you must set a dial-in conferencing region in the dial plan that is associated with the new dial-in access number.</span></span> <span data-ttu-id="66d8f-107">Plusieurs plans de numérotation peuvent utiliser la même région.</span><span class="sxs-lookup"><span data-stu-id="66d8f-107">Multiple dial plans can use the same region.</span></span>



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a><span data-ttu-id="66d8f-108">Pour créer ou modifier un numéro d’accès entrant</span><span class="sxs-lookup"><span data-stu-id="66d8f-108">To create or modify a dial-in access number</span></span>

1.  <span data-ttu-id="66d8f-109">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="66d8f-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="66d8f-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66d8f-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="66d8f-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="66d8f-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="66d8f-112">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Numéro d’accès entrant**.</span><span class="sxs-lookup"><span data-stu-id="66d8f-112">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="66d8f-113">Sur la page **numéro d’accès entrant** , effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="66d8f-113">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="66d8f-114">Cliquez sur **nouveau** pour ouvrir **le nouveau numéro d’accès entrant**.</span><span class="sxs-lookup"><span data-stu-id="66d8f-114">Click **New** to open **New Dial-in Access Number**.</span></span>
    
      - <span data-ttu-id="66d8f-115">Cliquez sur l’un des numéros d’accès entrant dans la liste, cliquez sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="66d8f-115">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="66d8f-116">L’utilisation du champ de recherche pour rechercher le contenu d’une colonne dans la liste des numéros d’accès entrant peut ne pas donner les résultats attendus.</span><span class="sxs-lookup"><span data-stu-id="66d8f-116">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="66d8f-117">Au lieu de cela, triez la liste selon la colonne qui vous intéresse pour identifier le numéro d’accès entrant que vous souhaitez afficher ou modifier.</span><span class="sxs-lookup"><span data-stu-id="66d8f-117">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span>

        
        </div>

5.  <span data-ttu-id="66d8f-118">Dans **numéro affiché**, tapez le numéro de téléphone que les utilisateurs du téléphone du réseau téléphonique commuté (PSTN) composent pour rejoindre une conférence.</span><span class="sxs-lookup"><span data-stu-id="66d8f-118">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66d8f-119">Ce numéro est affiché dans les invitations aux réunions et dans la page Web des paramètres de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="66d8f-119">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

6.  <span data-ttu-id="66d8f-120">Dans **nom d’affichage**, tapez une description pour le numéro d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="66d8f-120">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="66d8f-121">Il s’agit du nom associé au numéro d’accès entrant dans les résultats de la recherche Lync.</span><span class="sxs-lookup"><span data-stu-id="66d8f-121">This is the name that is associated with the dial-in access number in Lync search results.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66d8f-122">Ce nom s’affiche dans le client lorsqu’un utilisateur appelle le numéro d’accès.</span><span class="sxs-lookup"><span data-stu-id="66d8f-122">This name is displayed in the client when a user calls the access number.</span></span>

    
    </div>

7.  <span data-ttu-id="66d8f-123">Dans **URI de ligne**, tapez le numéro E. 164 du numéro d’accès entrant au format URI tel, y compris le symbole + avant le numéro et en excluant les espaces.</span><span class="sxs-lookup"><span data-stu-id="66d8f-123">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="66d8f-124">Par exemple, Tél : + 14255550200.</span><span class="sxs-lookup"><span data-stu-id="66d8f-124">For example, tel:+14255550200.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66d8f-125">Le même URI de ligne ne peut pas être réutilisé par un autre numéro d’accès à une conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="66d8f-125">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span>

    
    </div>

8.  <span data-ttu-id="66d8f-126">Dans **URI SIP**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="66d8f-126">In **SIP URI**, do the following:</span></span>
    
      - <span data-ttu-id="66d8f-127">Dans la zone de texte, tapez un URI SIP unique pour ce numéro d’accès à la Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="66d8f-127">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="66d8f-128">Cet URI SIP est affiché à différents emplacements, y compris, sans s’y limiter, les messages de notification d’appel et les versions antérieures des clients Communicator.</span><span class="sxs-lookup"><span data-stu-id="66d8f-128">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Communicator clients.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="66d8f-129">Le même URI SIP ne peut pas être réutilisé par un autre numéro d’accès à une conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="66d8f-129">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="66d8f-130">L’URI SIP ne peut pas être modifié une fois que le numéro d’accès est créé.</span><span class="sxs-lookup"><span data-stu-id="66d8f-130">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="66d8f-131">La seule façon de modifier l’URI SIP est de supprimer et de recréer le numéro d’accès.</span><span class="sxs-lookup"><span data-stu-id="66d8f-131">The only way to change the SIP URI is to delete and recreate the access number.</span></span>

        
        </div>
    
      - <span data-ttu-id="66d8f-132">Dans la zone de liste déroulante, cliquez sur le domaine de l’application de surveillance de conférence qui prend en charge ce numéro d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="66d8f-132">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>

9.  <span data-ttu-id="66d8f-133">Dans **pool**, cliquez sur le pool qui exécute l’instance du service Surveillance de conférence qui prend en charge ce numéro d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="66d8f-133">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66d8f-134">Si vous devez modifier le pool après avoir créé le numéro d’accès, vous devez utiliser l’applet de commande <STRONG>Move-CsApplicationEndpoint</STRONG> ou supprimer et recréer le numéro d’accès.</span><span class="sxs-lookup"><span data-stu-id="66d8f-134">If you need to change the pool after you create the access number, you must use the <STRONG>Move-CsApplicationEndpoint</STRONG> cmdlet or delete and recreate the access number.</span></span>

    
    </div>

10. <span data-ttu-id="66d8f-135">Dans **langue principale**, cliquez sur la langue dans laquelle les invites sont exécutées pour ce numéro d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="66d8f-135">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66d8f-136">La langue principale est la langue utilisée par le service Surveillance de conférence pour répondre à l’appel.</span><span class="sxs-lookup"><span data-stu-id="66d8f-136">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="66d8f-137">Les langues prises en charge sont affichées avec chaque numéro de téléphone d’accès dans la page Web paramètres de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="66d8f-137">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>

    
    </div>

11. <span data-ttu-id="66d8f-138">Module Dans **langues secondaires (quatre au maximum)**, cliquez sur **Ajouter**, sélectionnez une ou plusieurs langues supplémentaires que vous souhaitez prendre en charge pour les appelants vers ce numéro d’accès entrant, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="66d8f-138">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66d8f-139">Vous pouvez choisir jusqu’à quatre langues secondaires pour chaque numéro d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="66d8f-139">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="66d8f-140">Les utilisateurs peuvent sélectionner une langue secondaire avant d’entrer l’ID de conférence lorsqu’ils se connectent à une conférence.</span><span class="sxs-lookup"><span data-stu-id="66d8f-140">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>

    
    </div>

12. <span data-ttu-id="66d8f-141">Pour ajouter une région pour le numéro d’accès entrant, sous **régions associées**, cliquez sur **Ajouter**, cliquez sur une ou plusieurs régions associées aux plans de numérotation pour ce numéro d’accès entrant, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="66d8f-141">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>

13. <span data-ttu-id="66d8f-142">Pour supprimer une région du numéro d’accès entrant, sous **régions associées**, cliquez sur la région que vous souhaitez supprimer, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="66d8f-142">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>

14. <span data-ttu-id="66d8f-143">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="66d8f-143">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

