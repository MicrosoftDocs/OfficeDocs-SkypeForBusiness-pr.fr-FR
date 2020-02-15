---
title: 'Lync Server 2013 : vérifier la conception de la topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6968dfca2072ca9a6c0e5008528e27a14f01447
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a><span data-ttu-id="4f7ee-102">Vérifier la conception de la topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f7ee-102">Verify the topology design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f7ee-103">_**Dernière modification de la rubrique :** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="4f7ee-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="4f7ee-104">Le générateur de topologies vérifie automatiquement la topologie.</span><span class="sxs-lookup"><span data-stu-id="4f7ee-104">Topology Builder automatically verifies the topology.</span></span> <span data-ttu-id="4f7ee-105">Toute erreur de topologie est identifiée en tant qu’erreur de validation et signalée par l’icône d’erreur de validation en regard du rôle serveur.</span><span class="sxs-lookup"><span data-stu-id="4f7ee-105">Any topology error is identified as a validation error, indicated by the validation error icon next to the server role.</span></span> <span data-ttu-id="4f7ee-106">Il est également important de vérifier que la topologie représente correctement la topologie du déploiement.</span><span class="sxs-lookup"><span data-stu-id="4f7ee-106">It is important to also verify that the topology correctly represents the topology for your deployment.</span></span>

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a><span data-ttu-id="4f7ee-107">Pour vérifier la topologie avant la publication</span><span class="sxs-lookup"><span data-stu-id="4f7ee-107">To verify the topology prior to publication</span></span>

1.  <span data-ttu-id="4f7ee-108">Vérifiez que toutes les URL simples sont configurées correctement.</span><span class="sxs-lookup"><span data-stu-id="4f7ee-108">Check that all simple URLs are configured correctly.</span></span>

2.  <span data-ttu-id="4f7ee-109">Vérifiez que le serveur basé sur SQL Server est en ligne et disponible pour l’ordinateur sur lequel le générateur de topologies est installé, y compris les règles de pare-feu nécessaires.</span><span class="sxs-lookup"><span data-stu-id="4f7ee-109">Confirm that the SQL Server-based server is online and available to the computer where Topology Builder is installed, including any necessary firewall rules.</span></span>

3.  <span data-ttu-id="4f7ee-110">Confirmez que le partage de fichiers est disponible et qu’il dispose des autorisations appropriées qui ont été définies.</span><span class="sxs-lookup"><span data-stu-id="4f7ee-110">Confirm that the file share is available and has the proper permissions defined.</span></span>

4.  <span data-ttu-id="4f7ee-111">Confirmez que les rôles serveur corrects qui répondent à la configuration requise pour le déploiement sont définis dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="4f7ee-111">Confirm that the correct server roles that meet the deployment requirements are defined in the topology.</span></span>

5.  <span data-ttu-id="4f7ee-112">Vérifiez que les serveurs existent dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4f7ee-112">Verify that the servers exist in Active Directory Domain Services.</span></span> <span data-ttu-id="4f7ee-113">Cela se produit automatiquement si vous avez joint les serveurs au domaine.</span><span class="sxs-lookup"><span data-stu-id="4f7ee-113">This will happen automatically if you have joined the servers to the domain.</span></span>

<span data-ttu-id="4f7ee-114">Lorsque vous avez vérifié la topologie et qu’aucune erreur de validation n’a été détectée, vous êtes prêt à publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="4f7ee-114">When you have verified the topology and there are no validation errors, you should be ready to publish the topology.</span></span> <span data-ttu-id="4f7ee-115">Si des erreurs de validation sont détectées, vous devez les corriger pour pouvoir publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="4f7ee-115">If there are validation errors, you must correct these before you can publish the topology.</span></span> <span data-ttu-id="4f7ee-116">Pour plus d’informations sur la publication de votre topologie, voir [publier la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="4f7ee-116">For details about publishing your topology, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

