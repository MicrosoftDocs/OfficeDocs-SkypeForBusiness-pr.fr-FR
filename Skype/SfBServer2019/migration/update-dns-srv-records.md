---
title: Mettre à jour les enregistrements SRV DNS
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Domain Admins ou membre du groupe DnsAdmins.
ms.openlocfilehash: bf9f9c3f16ceb2ee35cda8e833d468e202d5653c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307055"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="90d99-103">Mettre à jour les enregistrements SRV DNS</span><span class="sxs-lookup"><span data-stu-id="90d99-103">Update DNS SRV records</span></span>

<span data-ttu-id="90d99-104">Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Domain Admins ou membre du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="90d99-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="90d99-105">Cette rubrique explique comment mettre à jour les enregistrements DNS (Domain Name System) après la migration vers Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="90d99-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="90d99-106">Après le déplacement de tous les utilisateurs vers Skype entreprise Server 2019, mais avant la désactivation du pool ou du réalisateur hérités, vous devez mettre à jour les enregistrements DNS SRV dans votre DNS interne pour chaque domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="90d99-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="90d99-107">Cette procédure part du principe que votre DNS interne comporte des zones pour vos domaines d’utilisateur SIP.</span><span class="sxs-lookup"><span data-stu-id="90d99-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="90d99-108">Pour configurer un enregistrement SRV DNS</span><span class="sxs-lookup"><span data-stu-id="90d99-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="90d99-109">Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="90d99-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="90d99-110">Dans l’arborescence de la console de votre domaine SIP, développez **zones de recherche directe**, développez le domaine SIP dans lequel Skype entreprise Server 2019 est installé, puis accédez au paramètre **_ TCP** .</span><span class="sxs-lookup"><span data-stu-id="90d99-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="90d99-111">Dans le volet droit, cliquez avec le bouton droit sur **_sipinternaltls** , puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="90d99-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="90d99-112">Dans la liste des **hôtes proposant ce service**, mettez à jour le nom de domaine complet (FQDN) de l’hôte pour qu’il pointe sur le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="90d99-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="90d99-113">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="90d99-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="90d99-114">Pour vérifier que le nom de domaine complet (FQDN) du pool frontal ou du serveur Standard Edition peut être résolu</span><span class="sxs-lookup"><span data-stu-id="90d99-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="90d99-115">Connectez-vous à un ordinateur client dans le domaine.</span><span class="sxs-lookup"><span data-stu-id="90d99-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="90d99-116">Cliquez sur \*\*Démarrer \*\*, puis sur \*\*Exécuter \*\*.</span><span class="sxs-lookup"><span data-stu-id="90d99-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="90d99-117">Dans la zone **ouvrir** , tapez cmd, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="90d99-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="90d99-118">À l’invite de commandes, tapez nslookup _ \<FQDN du pool\> frontal_ ou _ \<du FQDN du serveur\>Standard Edition_, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="90d99-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="90d99-119">Vérifiez que vous recevez une réponse qui est résolue en adresse IP appropriée pour le nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="90d99-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

