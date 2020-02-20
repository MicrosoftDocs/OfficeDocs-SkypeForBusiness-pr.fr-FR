---
title: Déplacer un seul utilisateur vers le pool pilote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 187b0b3055710f89b8c16d8167c1b6692d5eaac2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="d4c3e-102">Déplacer un seul utilisateur vers le pool pilote</span><span class="sxs-lookup"><span data-stu-id="d4c3e-102">Move a single user to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4c3e-103">_**Dernière modification de la rubrique :** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="d4c3e-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="d4c3e-104">Vous pouvez déplacer un utilisateur de votre pool Lync Server 2010 vers votre pool Lync Server 2013 pilote à l’aide du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d4c3e-104">You can move a user from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="d4c3e-105">Dans l’exemple ci-dessous, dans la colonne pool de serveurs d’inscriptions, **pool01.contoso.net** est le pool Lync Server 2010 et tous les six de ces utilisateurs sont connectés à ce pool.</span><span class="sxs-lookup"><span data-stu-id="d4c3e-105">In the example below, in the Registrar pool column, **pool01.contoso.net** is the Lync Server 2010 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="d4c3e-106">Utilisez les procédures suivantes pour déplacer un utilisateur vers votre pool Lync Server 2013 à l’aide du panneau de configuration Lync Server 2013 et de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d4c3e-106">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="d4c3e-107">Pour déplacer un utilisateur à l’aide du panneau de configuration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4c3e-107">To move a user by using the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="d4c3e-108">**Liste des utilisateurs dans le panneau de configuration Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="d4c3e-108">**List of users in the Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="d4c3e-109">![Panneau de configuration Lync Server, boîte de dialogue déplacer un utilisateur](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Panneau de configuration Lync Server, boîte de dialogue déplacer un utilisateur")</span><span class="sxs-lookup"><span data-stu-id="d4c3e-109">![Lync Server Control Panel, Move User dialog](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server Control Panel, Move User dialog")</span></span>

1.  <span data-ttu-id="d4c3e-110">Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou membre du rôle d’administrateur CsAdministrator ou CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d4c3e-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="d4c3e-111">Ouvrez le **Panneau de configuration Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d4c3e-111">Open **Lync Server Control Panel**.</span></span>

3.  <span data-ttu-id="d4c3e-112">Cliquez sur **Utilisateurs**, sur Rechercher, puis sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="d4c3e-112">Click **Users**, click Search, and then click **Find**.</span></span>

4.  <span data-ttu-id="d4c3e-113">Sélectionnez un utilisateur que vous souhaitez déplacer vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d4c3e-113">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="d4c3e-114">Dans cet exemple, nous allons déplacer l’utilisateur Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="d4c3e-114">In this example, we will move user Sara Davis.</span></span>

5.  <span data-ttu-id="d4c3e-115">Dans le menu **Action**, sélectionnez **Déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="d4c3e-115">On the **Action** menu, select **Move selected users to pool**.</span></span>

6.  <span data-ttu-id="d4c3e-116">Dans la liste déroulante, sélectionnez le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d4c3e-116">From the drop-down list, select the Lync Server 2013 pool.</span></span>

7.  <span data-ttu-id="d4c3e-117">Cliquez sur **Action**, puis sur **Déplacer les utilisateurs sélectionnés vers le pool**.</span><span class="sxs-lookup"><span data-stu-id="d4c3e-117">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="d4c3e-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4c3e-118">Click **OK**.</span></span>
    
    <span data-ttu-id="d4c3e-119">![Boîte de dialogue déplacer des utilisateurs, pool de serveurs d’inscriptions de destination](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Boîte de dialogue déplacer des utilisateurs, pool de serveurs d’inscriptions de destination")</span><span class="sxs-lookup"><span data-stu-id="d4c3e-119">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

8.  <span data-ttu-id="d4c3e-120">Vérifiez que la colonne pool de serveurs d' **inscriptions** de l’utilisateur contient désormais le pool Lync Server 2013, ce qui indique que l’utilisateur a été déplacé avec succès.</span><span class="sxs-lookup"><span data-stu-id="d4c3e-120">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="d4c3e-121">Pour déplacer un utilisateur à l’aide de Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="d4c3e-121">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="d4c3e-122">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d4c3e-122">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="d4c3e-123">Sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d4c3e-123">At the command line, type the following:</span></span>
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="d4c3e-124">Ensuite, sur la ligne de commande, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d4c3e-124">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="d4c3e-125">L’identité **RegistrarPool** pointe désormais vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d4c3e-125">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="d4c3e-126">Le présence de cette identité confirme que l’utilisateur a été déplacé avec succès.</span><span class="sxs-lookup"><span data-stu-id="d4c3e-126">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="d4c3e-127">![Sortie de l’applet de commande Get-CsUser avec le filtre d’identité](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Sortie de l’applet de commande Get-CsUser avec le filtre d’identité")</span><span class="sxs-lookup"><span data-stu-id="d4c3e-127">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d4c3e-128">Pour plus d’informations sur l’applet de commande <STRONG>Get-CsUser</STRONG>, exécutez : <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span><span class="sxs-lookup"><span data-stu-id="d4c3e-128">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

