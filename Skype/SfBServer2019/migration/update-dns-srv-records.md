---
title: Mettre à jour les enregistrements SRV DNS
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.
ms.openlocfilehash: 26bb80618868a2bec03d1de32f6c010869b8cf8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753266"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="f6955-103">Mettre à jour les enregistrements SRV DNS</span><span class="sxs-lookup"><span data-stu-id="f6955-103">Update DNS SRV records</span></span>

<span data-ttu-id="f6955-104">Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="f6955-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="f6955-105">Cette rubrique décrit comment mettre à jour les enregistrements DNS (Domain Name System) après la migration vers Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f6955-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="f6955-106">Une fois que tous les utilisateurs ont été déplacés vers Skype Entreprise Server 2019, mais avant la désaffectation du pool ou du directeur hérité, vous devez mettre à jour les enregistrements DNS SRV dans votre DNS interne pour chaque domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="f6955-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="f6955-107">Cela présuppose que votre serveur DNS interne comporte des zones pour vos domaines utilisateur SIP.</span><span class="sxs-lookup"><span data-stu-id="f6955-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="f6955-108">Pour configurer un enregistrement DNS SRV</span><span class="sxs-lookup"><span data-stu-id="f6955-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="f6955-109">Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f6955-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="f6955-110">Dans l’arborescence de la console pour votre domaine SIP, développez zones de recherche **avant,** développez le domaine SIP dans lequel Skype Entreprise Server 2019 est installé et accédez au **paramètre _tcp.**</span><span class="sxs-lookup"><span data-stu-id="f6955-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="f6955-111">Dans le volet droit, cliquez avec le bouton **droit sur _sipinternaltls** puis sélectionnez **Propriétés.**</span><span class="sxs-lookup"><span data-stu-id="f6955-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="f6955-112">Dans **l’offre hôte de ce service,** mettez à jour le nom de domaine complet de l’hôte pour qu’il pointe vers le pool Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f6955-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="f6955-113">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6955-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="f6955-114">Pour vérifier que le nom de domaine complet du pool frontal ou du serveur Standard Edition peut être résolu</span><span class="sxs-lookup"><span data-stu-id="f6955-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="f6955-115">Ouvrez une session sur un ordinateur client du domaine.</span><span class="sxs-lookup"><span data-stu-id="f6955-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="f6955-116">Cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f6955-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="f6955-117">Dans la **zone Ouvrir,** tapez cmd, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="f6955-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="f6955-118">À l’invite de commandes, tapez nslookup _\<FQDN of the Front End pool\>_ ou  _\<FQDN of the Standard Edition server\>_ , puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="f6955-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="f6955-119">Vérifiez que vous recevez une réponse qui est résolue en adresse IP appropriée pour le nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="f6955-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

