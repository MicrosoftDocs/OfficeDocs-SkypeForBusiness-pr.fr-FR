---
title: Autoriser la connexion au serveur Edge Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64786c29027c99de2f3b5e01846a5283ec57a084
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42003979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="75b36-102">Autoriser la connexion au serveur Edge Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="75b36-102">Authorize connection to Office Communications Server 2007 R2 Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75b36-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="75b36-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="75b36-104">Pour chaque serveur frontal Lync Server 2013 ou serveur Standard Edition dans votre pool pilote, vous devez mettre à jour la liste des serveurs internes autorisés à se connecter au serveur Edge Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="75b36-104">For each Lync Server 2013 Front End Server or Standard Edition server in your pilot pool, you must update the list of internal servers that are authorized to connect to the Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="75b36-105">Sans ces mises à jour, les conférences audio/vidéo (A/V) externes ne peuvent pas fonctionner pour les participants qui utilisent un serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="75b36-105">Without these updates, external audio/visual (A/V) conferencing for users joining by using the legacy Edge Server will not work.</span></span>

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="75b36-106">Pour autoriser la connexion au serveur Edge Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="75b36-106">To Authorize Connection to Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="75b36-107">À partir du serveur Edge Office Communications Server 2007 R2, à partir du groupe **Outils d’administration** , ouvrez le composant logiciel enfichable Gestion de l' **ordinateur** .</span><span class="sxs-lookup"><span data-stu-id="75b36-107">From the Office Communications Server 2007 R2 Edge Server, from the **Administrative Tools** group, open the **Computer Management** snap-in.</span></span>

2.  <span data-ttu-id="75b36-108">Dans l’arborescence de la console, développez **Services et applications**.</span><span class="sxs-lookup"><span data-stu-id="75b36-108">In the console tree, expand **Services and Applications**.</span></span>

3.  <span data-ttu-id="75b36-109">Cliquez avec le bouton droit sur **Office Communications Server 2007 R2**, puis sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="75b36-109">Right-click **Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="75b36-110">Cliquez sur l’onglet **Interne**.</span><span class="sxs-lookup"><span data-stu-id="75b36-110">Click the **Internal** tab.</span></span>

5.  <span data-ttu-id="75b36-111">Sous **Ajouter un serveur**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="75b36-111">Under **Add Server**, click **Add**.</span></span>

6.  <span data-ttu-id="75b36-112">Dans la boîte de dialogue **Ajouter Office Communications Server**, entrez les informations appropriées :</span><span class="sxs-lookup"><span data-stu-id="75b36-112">In the **Add Office Communications Server** dialog box, enter the appropriate information:</span></span>
    
      - <span data-ttu-id="75b36-113">Spécifiez le nom de domaine complet (FQDN) de chaque serveur frontal Lync Server 2013 ou serveur Standard Edition, ainsi que le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75b36-113">Specify the fully qualified domain name (FQDN) of each Lync Server 2013 Front End Server or Standard Edition server, and Lync Server 2013 pool.</span></span>
    
      - <span data-ttu-id="75b36-114">Spécifiez le nom de domaine complet (FQDN) du directeur Lync Server 2013 si vous avez configuré un itinéraire statique sur le pool qui spécifie l’ordinateur du tronçon suivant par son nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="75b36-114">Specify the FQDN of the Lync Server 2013 Director if you configured a static route on the pool that specifies the next hop computer by its FQDN.</span></span>

7.  <span data-ttu-id="75b36-115">Une fois que vous avez ajouté une entrée pour chaque Lync Server 2013, serveur frontal, serveur Standard Edition, pool et directeur, cliquez sur **appliquer** , puis sur **OK** pour fermer la page Propriétés.</span><span class="sxs-lookup"><span data-stu-id="75b36-115">After you have added an entry for each Lync Server 2013, Front End Server, Standard Edition server, pool, and Director, click **Apply** and then click **OK** to close the Properties page.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

