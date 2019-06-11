---
title: Connexion à Lync 2013 et utilisation sur l’ordinateur virtuel
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3b890f008b30ecf008bd2e6f03803fbfe6c1674
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a><span data-ttu-id="c9179-102">Connexion à Lync 2013 et utilisation sur l’ordinateur virtuel</span><span class="sxs-lookup"><span data-stu-id="c9179-102">Signing in and using Lync 2013 on the virtual machine</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9179-103">_**Dernière modification de la rubrique:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="c9179-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="c9179-104">Une fois que le plug-in VDI est activé, les étapes suivantes se produisent lorsque l’utilisateur se connecte à Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c9179-104">After the VDI plug-in is enabled, the following steps occur when the user signs in to Lync 2013.</span></span>

1.  <span data-ttu-id="c9179-105">L’utilisateur tape ses informations d’identification dans le client 2013 Lync exécuté sur l’ordinateur virtuel.</span><span class="sxs-lookup"><span data-stu-id="c9179-105">The user types his or her credentials in to the Lync 2013 client running on the virtual machine.</span></span>

2.  <span data-ttu-id="c9179-106">Après que Lync a détecté la disponibilité du plug-in VDI, Lync invite l’utilisateur à entrer à nouveau ses informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="c9179-106">After Lync detects the availability of the VDI plug-in, Lync prompts the user to re-enter his or her credentials.</span></span> <span data-ttu-id="c9179-107">Dans cette boîte de dialogue, nous recommandons à l’utilisateur d’activer la case à cocher **Enregistrer mon mot de passe** afin qu’il n’ait pas à les entrer de nouveau lors de connexions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="c9179-107">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>

3.  <span data-ttu-id="c9179-108">Lync entame le jumelage avec le plug-in VDI.</span><span class="sxs-lookup"><span data-stu-id="c9179-108">Lync begins pairing with the VDI plug-in.</span></span> <span data-ttu-id="c9179-109">Avant de procéder à un jumelage, le client affiche deux icônes dans la barre d’État Lync.</span><span class="sxs-lookup"><span data-stu-id="c9179-109">Before pairing is complete, the client displays two icons in the Lync status bar.</span></span> <span data-ttu-id="c9179-110">L’icône située dans le coin inférieur gauche indique qu’aucun périphérique audio n’est disponible et que l’icône clignotant dans le coin inférieur droit indique que le jumelage VDI est en cours, comme illustré ci-dessous:</span><span class="sxs-lookup"><span data-stu-id="c9179-110">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that the VDI pairing is in progress, as shown:</span></span>
    
    <span data-ttu-id="c9179-111">![Icône VDI de Lync montrant une jumelage réussie] (images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Icône VDI de Lync montrant une jumelage réussie")</span><span class="sxs-lookup"><span data-stu-id="c9179-111">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>  

4.  <span data-ttu-id="c9179-112">Une fois le jumelage VDI réussi, les icônes changent pour indiquer le périphérique audio qui sera utilisé pour les appels et la réussite du jumelage VDI :</span><span class="sxs-lookup"><span data-stu-id="c9179-112">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success:</span></span>
    
    <span data-ttu-id="c9179-113">![Icône d’appariement VDI de Lync indiquant le succès] (images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Icône d’appariement VDI de Lync indiquant le succès")</span><span class="sxs-lookup"><span data-stu-id="c9179-113">![Lync VDI pairing icon showing success](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Lync VDI pairing icon showing success")</span></span>  

5.  <span data-ttu-id="c9179-114">Après paires Lync avec le plug-in VDI, l’utilisateur peut voir son statut de connexion sur les appareils compatibles Lync qui sont connectés à l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="c9179-114">After Lync pairs with the VDI plug-in, the user can see his or her presence on Lync compatible devices that are connected to the local computer.</span></span> <span data-ttu-id="c9179-115">L’utilisateur peut désormais passer et répondre aux appels comme d’habitude.</span><span class="sxs-lookup"><span data-stu-id="c9179-115">The user can now place and answer calls as usual.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

