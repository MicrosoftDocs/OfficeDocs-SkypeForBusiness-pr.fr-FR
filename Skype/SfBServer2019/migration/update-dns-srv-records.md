---
title: Mettre à jour les enregistrements SRV DNS
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou un membre du groupe DnsAdmins.
ms.openlocfilehash: 5cdf98d065abbb57b3cb654c8b770f8f1f87500c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231382"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="eb391-103">Mettre à jour les enregistrements SRV DNS</span><span class="sxs-lookup"><span data-stu-id="eb391-103">Update DNS SRV records</span></span>

<span data-ttu-id="eb391-104">Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou un membre du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="eb391-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="eb391-105">Cette rubrique décrit comment mettre à jour les enregistrements de nom de domaine DNS (Domain Name System) après la migration vers Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="eb391-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="eb391-106">Une fois que tous les utilisateurs ont été déplacés vers Skype pour Business Server 2019, mais avant que le pool hérité ou un directeur est désactivé, vous devez mettre à jour les enregistrements DNS SRV dans votre DNS interne pour chaque domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="eb391-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="eb391-107">Cette procédure suppose que votre serveur DNS interne comporte des zones pour vos domaines utilisateur SIP.</span><span class="sxs-lookup"><span data-stu-id="eb391-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="eb391-108">Pour configurer un enregistrement DNS SRV</span><span class="sxs-lookup"><span data-stu-id="eb391-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="eb391-109">Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis cliquez sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="eb391-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="eb391-110">Dans l’arborescence de la console pour votre domaine SIP, développez **Zones de recherche directes**, développez le domaine SIP dans le Skype pour Business Server 2019 est installé, puis accédez au paramètre **_tcp** .</span><span class="sxs-lookup"><span data-stu-id="eb391-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="eb391-111">Dans le volet droit, cliquez sur **_sipinternaltls** et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="eb391-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="eb391-112">Dans **hôte offrant ce service**, mettez à jour le nom de domaine complet pour pointer vers le Skype pour le pool d’entreprise Server 2019 hôte.</span><span class="sxs-lookup"><span data-stu-id="eb391-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="eb391-113">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb391-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="eb391-114">Pour vérifier que le nom de domaine complet du pool frontal ou serveur Standard Edition server peut être résolu</span><span class="sxs-lookup"><span data-stu-id="eb391-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="eb391-115">Ouvrez une session un ordinateur client du domaine.</span><span class="sxs-lookup"><span data-stu-id="eb391-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="eb391-116">Cliquez sur \*\*Démarrer \*\*, puis sur \*\*Exécuter \*\*.</span><span class="sxs-lookup"><span data-stu-id="eb391-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="eb391-117">Dans la zone **Ouvrir** , tapez cmd, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb391-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="eb391-118">À l’invite de commandes, tapez nslookup _ \<nom de domaine complet du pool frontal\> _ ou _ \<nom de domaine complet du serveur Standard Edition\>_, puis appuyez sur ENTRÉE.</span><span class="sxs-lookup"><span data-stu-id="eb391-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="eb391-119">Vérifiez que vous recevez une réponse qui est résolu en adresse IP appropriée pour le nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="eb391-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

