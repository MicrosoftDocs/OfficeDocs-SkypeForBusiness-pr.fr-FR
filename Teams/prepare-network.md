---
title: Préparer le réseau de votre organisation pour Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: En savoir plus sur la préparation du réseau de votre organisation pour Microsoft Teams (exigences réseau, optimisation du réseau, besoins en matière de bande passante, etc.).
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: db911db3631caebb0e767401f80c36bdac6c9c1b
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420829"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="2f8f8-103">Préparer le réseau de votre organisation pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f8f8-103">Prepare your organization's network for Microsoft Teams</span></span> 

## <a name="network-requirements"></a><span data-ttu-id="2f8f8-104">Configuration réseau requise</span><span class="sxs-lookup"><span data-stu-id="2f8f8-104">Network requirements</span></span>

<span data-ttu-id="2f8f8-105">Si vous avez déjà [optimisé votre réseau pour Microsoft 365 ou Office 365](/Office365/Enterprise/assessing-network-connectivity), vous êtes probablement prêt pour Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-105">If you've already [optimized your network for Microsoft 365 or Office 365](/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams.</span></span> <span data-ttu-id="2f8f8-106">Dans tous les cas, et surtout si vous déployez rapidement Teams en tant que première charge de travail Microsoft 365 ou Office 365 pour prendre en charge les **employés distants**, vérifiez les étapes suivantes avant de commencer le déploiement de Teams :</span><span class="sxs-lookup"><span data-stu-id="2f8f8-106">In any case - and especially if you're rolling out Teams quickly as your first Microsoft 365 or Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:</span></span>

1.  <span data-ttu-id="2f8f8-107">Est-ce que tous vos emplacements ont un accès à Internet (pour pouvoir se connecter à Microsoft 365 ou à Office 365) ?</span><span class="sxs-lookup"><span data-stu-id="2f8f8-107">Do all your locations have internet access (so they can connect to Microsoft 365 or Office 365)?</span></span> <span data-ttu-id="2f8f8-108">En plus du trafic web normal, assurez-vous d’avoir ouvert les ports TCP et les adresses IP répertoriés pour Teams dans [URL Office 365 et les plages d’adresses IP](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="2f8f8-108">In addition to normal web traffic, make sure you've opened the TCP ports and IP addresses listed for Teams in [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2f8f8-109">Si vous devez vous fédérer avec Skype pour les entreprises, sur site ou en ligne, vous devrez configurer un enregistrement DNS supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-109">If you need to federate with Skype for Business, either on-premises or online, you will need to configure an additional DNS record.</span></span>
    >
    >|<span data-ttu-id="2f8f8-110">Enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="2f8f8-110">DNS record</span></span>  |<span data-ttu-id="2f8f8-111">Service</span><span class="sxs-lookup"><span data-stu-id="2f8f8-111">Service</span></span>  |<span data-ttu-id="2f8f8-112">Protocol (Protocole)</span><span class="sxs-lookup"><span data-stu-id="2f8f8-112">Protocol</span></span>  |<span data-ttu-id="2f8f8-113">Priority (Priorité)</span><span class="sxs-lookup"><span data-stu-id="2f8f8-113">Priority</span></span>  |<span data-ttu-id="2f8f8-114">Weight (Poids)</span><span class="sxs-lookup"><span data-stu-id="2f8f8-114">Weight</span></span>  |<span data-ttu-id="2f8f8-115">Port</span><span class="sxs-lookup"><span data-stu-id="2f8f8-115">Port</span></span>  |<span data-ttu-id="2f8f8-116">Target (Cible)</span><span class="sxs-lookup"><span data-stu-id="2f8f8-116">Target</span></span>  |
    >|---------|---------|---------|---------|---------|---------|---------|
    >|<span data-ttu-id="2f8f8-117">SRV</span><span class="sxs-lookup"><span data-stu-id="2f8f8-117">SRV</span></span>     |<span data-ttu-id="2f8f8-118">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="2f8f8-118">sipfederationtls</span></span>     |<span data-ttu-id="2f8f8-119">TCP</span><span class="sxs-lookup"><span data-stu-id="2f8f8-119">TCP</span></span>     |<span data-ttu-id="2f8f8-120">100</span><span class="sxs-lookup"><span data-stu-id="2f8f8-120">100</span></span>     |<span data-ttu-id="2f8f8-121">1</span><span class="sxs-lookup"><span data-stu-id="2f8f8-121">1</span></span>     |<span data-ttu-id="2f8f8-122">5061</span><span class="sxs-lookup"><span data-stu-id="2f8f8-122">5061</span></span>     |<span data-ttu-id="2f8f8-123">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2f8f8-123">sipfed.online.lync.com</span></span>     |
    
2.  <span data-ttu-id="2f8f8-124">Avez-vous un domaine vérifié pour Microsoft 365 ou Office 365 (par exemple, contoso.com) ?</span><span class="sxs-lookup"><span data-stu-id="2f8f8-124">Do you have a verified domain for Microsoft 365 or Office 365 (for example, contoso.com)?</span></span>
    
    - <span data-ttu-id="2f8f8-125">Si votre organisation n’a pas déployé Microsoft 365 ou Office 365, consultez la [prise en main](/microsoft-365/admin/admin-overview/get-started-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="2f8f8-125">If your organization hasn't rolled out Microsoft 365 or Office 365, see [Get started](/microsoft-365/admin/admin-overview/get-started-with-office-365).</span></span>
    - <span data-ttu-id="2f8f8-126">Si votre organisation n’a pas ajouté ou configuré un domaine vérifié pour Microsoft 365 ou Office 365, consultez là [FAQ sur les domaines](/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="2f8f8-126">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see the [Domains FAQ](/microsoft-365/admin/setup/domains-faq).</span></span>

3.  <span data-ttu-id="2f8f8-127">Votre organisation a-t-elle déployé Exchange Online et SharePoint Online ?</span><span class="sxs-lookup"><span data-stu-id="2f8f8-127">Has your organization deployed Exchange Online and SharePoint Online?</span></span>
    
    - <span data-ttu-id="2f8f8-128">Si votre organisation ne dispose pas d'Exchange Online, reportez-vous à la page [Comprendre l’interaction entre Exchange et Microsoft Teams](exchange-teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="2f8f8-128">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact.md).</span></span>
    - <span data-ttu-id="2f8f8-129">Si votre organisation ne dispose pas de SharePoint Online, reportez-vous à la page [Comprendre l’interaction entre SharePoint Online et OneDrive Entreprise avec Microsoft Teams](sharepoint-onedrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="2f8f8-129">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

<span data-ttu-id="2f8f8-130">Une fois que vous avez vérifié que vous répondez à ces exigences réseau, vous êtes prêt à [déployer Teams](./deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2f8f8-130">Once you've verified that you meet these network requirements, you may be ready to [Roll out Teams](./deploy-overview.md).</span></span> <span data-ttu-id="2f8f8-131">Si vous êtes une grande entreprise multinationale ou si vous savez que vous avez des limites réseau, lisez la suite pour découvrir comment évaluer et optimiser votre réseau pour Teams.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-131">If you're a large multinational enterprise, or if you know you've got some network limitations, read on to learn how to assess and optimize your network for Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f8f8-132">**Pour les établissements d’enseignement** : si votre organisation est un établissement d’enseignement et que vous utilisez un système d’information sur les élèves (SIE), [déployez la synchronisation des données scolaires](/schooldatasync/) avant de déployer Teams.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-132">**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](/schooldatasync/) before you roll out Teams.</span></span>
>  
> <span data-ttu-id="2f8f8-133">**Exécution de Skype Entreprise Server** en local : si votre organisation exécute Skype Entreprise Server en local (ou Lync Server), vous devez [configurer Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) pour synchroniser votre annuaire local avec Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-133">**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Microsoft 365 or Office 365.</span></span>

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a><span data-ttu-id="2f8f8-134">Recommandation : surveillez votre réseau à l’aide du tableau de bord de qualité des appels et de l’analyse des appels</span><span class="sxs-lookup"><span data-stu-id="2f8f8-134">Best practice: Monitor your network using CQD and call analytics</span></span> 

<span data-ttu-id="2f8f8-135">Utilisez le [tableau de bord de la qualité des appels (TBQA)](turning-on-and-using-call-quality-dashboard.md) pour mieux connaître la qualité des appels et réunions dans Teams.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-135">Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to gain insight into the quality of calls and meetings in Teams.</span></span> <span data-ttu-id="2f8f8-136">Le TBQA peut vous aider à optimiser votre réseau en gardant un œil sur la qualité, la fiabilité et l’expérience utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-136">CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience.</span></span> <span data-ttu-id="2f8f8-137">Le TBQA examine la télémétrie d’agrégation pour l’ensemble d’une organisation où des modèles globaux peuvent apparaître, ce qui vous permet d’identifier les problèmes et de planifier la correction.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-137">CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation.</span></span> <span data-ttu-id="2f8f8-138">De plus, le TBQA propose des rapports métriques enrichis qui fournissent des informations sur la qualité globale, sur la fiabilité et sur l’expérience utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-138">Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.</span></span> 

<span data-ttu-id="2f8f8-139">Vous utiliserez [l’analyse des appels](set-up-call-analytics.md) pour évaluer les problèmes liés aux appels et aux réunions pour un utilisateur particulier.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-139">You'll use [call analytics](set-up-call-analytics.md) to investigate call and meeting problems for an individual user.</span></span>

## <a name="network-optimization"></a><span data-ttu-id="2f8f8-140">Optimisation réseau</span><span class="sxs-lookup"><span data-stu-id="2f8f8-140">Network optimization</span></span>

<span data-ttu-id="2f8f8-141">Les tâches suivantes sont facultatives et ne sont pas requises pour déployer Teams, en particulier si vous êtes une petite entreprise et que vous avez déjà déployé Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-141">The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you've already rolled out Microsoft 365 or Office 365.</span></span> <span data-ttu-id="2f8f8-142">Utilisez ces instructions pour optimiser les performances de votre réseau et de Teams, ou si vous savez que vous avez certaines limitations de réseau.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-142">Use this guidance to optimize your network and Teams performance or if you know you've got some network limitations.</span></span>

<span data-ttu-id="2f8f8-143">Vous pouvez avoir besoin d’optimiser davantage le réseau si :</span><span class="sxs-lookup"><span data-stu-id="2f8f8-143">You might want to do additional network optimization if:</span></span>

  - <span data-ttu-id="2f8f8-144">Teams fonctionnent lentement (votre bande passante est peut-être insuffisante)</span><span class="sxs-lookup"><span data-stu-id="2f8f8-144">Teams runs slowly (maybe you have insufficient bandwidth)</span></span>
  - <span data-ttu-id="2f8f8-145">Les appels sont en continue (peut être dû à un pare-feu ou à des bloqueurs de proxy)</span><span class="sxs-lookup"><span data-stu-id="2f8f8-145">Calls keep dropping (might be due to firewall or proxy blockers)</span></span>
  - <span data-ttu-id="2f8f8-146">Les appels sont statiques et saccadés, ou la voix est robotique (peut être dû à une gigue ou une perte de paquets)</span><span class="sxs-lookup"><span data-stu-id="2f8f8-146">Calls have static and cut out, or voices sound like robots (could be jitter or packet loss)</span></span>

<span data-ttu-id="2f8f8-147">Pour une discussion détaillée sur l’optimisation du réseau, ainsi que des instructions sur l’identification et la résolution des problèmes de réseau, lisez les [principes de connectivité réseau de Microsoft 365 et Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).</span><span class="sxs-lookup"><span data-stu-id="2f8f8-147">For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, read [Microsoft 365 and Office 365 Network Connectivity Principles](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="2f8f8-148">Tâche d'optimisation du réseau</span><span class="sxs-lookup"><span data-stu-id="2f8f8-148">Network optimization task</span></span></th>
<th><span data-ttu-id="2f8f8-149">Détails</span><span class="sxs-lookup"><span data-stu-id="2f8f8-149">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="2f8f8-150">Planificateur de réseau</span><span class="sxs-lookup"><span data-stu-id="2f8f8-150">Network planner</span></span></td>
<td><p><span data-ttu-id="2f8f8-151">Pour obtenir de l’aide sur l’évaluation de votre réseau, notamment les calculs de bande passante et les exigences réseau au sein des emplacements physiques de votre organisation, consultez l’outil <a href="/microsoftteams/network-planner">Planificateur réseau</a> dans le <a href="https://admin.teams.microsoft.com">centre d’administration Teams</a>.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-151">For help assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the <a href="/microsoftteams/network-planner">Network Planner</a> tool, in the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="2f8f8-152">Lorsque vous indiquez les détails de votre réseau et de votre utilisation de Teams, le planificateur de réseau calcule les exigences réseau requises pour le déploiement de Teams et de Voix Cloud dans les emplacements physiques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-152">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span></p>
<p><span data-ttu-id="2f8f8-153">Pour voir un exemple de scénario, consultez <a href="/microsoftteams/tutorial-network-planner-example">Utilisation du planificateur réseau : exemple de scénario</a>.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-153">For an example scenario, see <a href="/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2f8f8-154">Conseiller pour Teams</span><span class="sxs-lookup"><span data-stu-id="2f8f8-154">Advisor for Teams</span></span></td>
<td><span data-ttu-id="2f8f8-155"><a href="/microsoftteams/use-advisor-teams-roll-out">Conseiller pour Teams</a> fait partie intégrante du <a href="https://admin.teams.microsoft.com">Centre d’administration Teams</a>.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-155"><a href="/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> is part of the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="2f8f8-156">Il évalue votre environnement Microsoft 365 ou Office 365 et identifie les configurations les plus courantes que vous devrez peut-être mettre à jour ou modifier avant de pouvoir déployer Teams.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-156">It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2f8f8-157">Résolution des noms externes</span><span class="sxs-lookup"><span data-stu-id="2f8f8-157">External Name Resolution</span></span></td>
<td><span data-ttu-id="2f8f8-158">Assurez-vous que tous les ordinateurs exécutant le client Teams peuvent résoudre des requêtes DNS externes pour découvrir les services fournis par Microsoft 365 ou Office 365 et que vos pare-feu n’empêchent pas l’accès.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-158">Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Microsoft 365 or Office 365 and that your firewalls are not preventing access.</span></span> <span data-ttu-id="2f8f8-159">Pour plus d’informations sur la configuration des ports de pare-feu, consultez <a href="/microsoftteams/office-365-urls-ip-address-ranges">URL et plages d’adresses IP Microsoft 365 et Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-159">For information about configuring firewall ports, go to <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 and Office 365 URLs and IP ranges</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2f8f8-160">Tenir à jour les sessions</span><span class="sxs-lookup"><span data-stu-id="2f8f8-160">Maintain session persistence</span></span></td>
<td><span data-ttu-id="2f8f8-161">Assurez-vous que votre pare-feu ne modifie pas les traductions d’adresses réseau (NAT) mappées ou les ports pour UDP.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-161">Make sure your firewall doesn't change the mapped Network Address Translation (NAT) addresses or ports for UDP.</span></span></td>
</tr><tr class="odd">
<td><span data-ttu-id="2f8f8-162">Valider la taille du pool NAT</span><span class="sxs-lookup"><span data-stu-id="2f8f8-162">Validate NAT pool size</span></span></td>
<td><span data-ttu-id="2f8f8-163">Validez la taille du pool traduction d’adresses réseau (NAT) requise pour la connectivité des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-163">Validate the network address translation (NAT) pool size required for user connectivity.</span></span> <span data-ttu-id="2f8f8-164">Lorsque plusieurs utilisateurs et appareils accèdent à Microsoft 365 ou Office 365 à l’aide de la <a href="/office365/enterprise/nat-support-with-office-365">traduction d’adresses réseau (NAT) ou de la traduction d’adresses de port (PAT)</a>, vous devez vous assurer que les appareils cachés derrière chaque adresse IP routable publiquement ne dépassent pas le nombre pris en charge.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-164">When multiple users and devices access Microsoft 365 or Office 365 using <a href="/office365/enterprise/nat-support-with-office-365">Network Address Translation (NAT) or Port Address Translation (PAT)</a>, you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span> <span data-ttu-id="2f8f8-165">Assurez-vous que des adresses IP publiques adéquates sont affectées aux pools NAT afin d’éviter une insuffisance de ports.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-165">Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="2f8f8-166">L’insuffisance de ports contribue à l’incapacité des utilisateurs et appareils internes à se connecter au service Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-166">Port exhaustion will contribute to internal users and devices being unable to connect to the Microsoft 365 or Office 365 service.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2f8f8-167">Routage vers des centres de données Microsoft</span><span class="sxs-lookup"><span data-stu-id="2f8f8-167">Routing to Microsoft data centers</span></span></td>
<td><span data-ttu-id="2f8f8-168"><a href="/office365/enterprise/client-connectivity">Implémenter le routage le plus efficace vers les centres de données Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-168"><a href="/office365/enterprise/client-connectivity">Implement the most efficient routing to Microsoft data centers</a>.</span></span> <span data-ttu-id="2f8f8-169">Identifiez les emplacements qui peuvent utiliser les points de sortie locaux ou régionaux pour vous connecter au réseau Microsoft le plus efficacement possible.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-169">Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2f8f8-170">Guide sur la détection et la prévention des intrusions</span><span class="sxs-lookup"><span data-stu-id="2f8f8-170">Intrusion Detection and Prevention Guidance</span></span></td>
<td><span data-ttu-id="2f8f8-171">Si votre environnement possède un système de <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">détection d’intrusions</a> ou un système de prévention (IDS ou IPS) déployé pour disposer d’une sécurité supplémentaire pour les connexions sortantes, n’oubliez pas d’autoriser toutes les URL Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-171">If your environment has an <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to allow all Microsoft 365 or Office 365 URLs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2f8f8-172">Configurer un VPN en tunnel segmenté</span><span class="sxs-lookup"><span data-stu-id="2f8f8-172">Configure split-tunnel VPN</span></span></td>
<td><p><span data-ttu-id="2f8f8-173">Nous vous recommandons de fournir un autre chemin d’accès pour le trafic Teams qui contourne le réseau privé virtuel (VPN), communément appelé <a href="/windows/security/identity-protection/vpn/vpn-routing">VPN en tunnel segmenté</a>.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-173">We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as <a href="/windows/security/identity-protection/vpn/vpn-routing">split-tunnel VPN</a>.</span></span> <span data-ttu-id="2f8f8-174">Grâce au tunnel segmenté, le trafic pour Microsoft 365 ou Office 365 ne passe pas par le VPN, mais va directement vers Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-174">Split tunneling means that traffic for Microsoft 365 or Office 365 doesn't go through the VPN but instead goes directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="2f8f8-175">Contourner le VPN a un impact positif sur la qualité de Teams et réduit la charge à partir des appareils VPN et du réseau de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-175">Bypassing your VPN will have a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network.</span></span> <span data-ttu-id="2f8f8-176">Pour mettre en place un tunnel segmenté, consultez votre fournisseur VPN.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-176">To implement a split-tunnel VPN, work with your VPN vendor.</span></span></p>
<p><span data-ttu-id="2f8f8-177">Nous vous recommandons de contourner le VPN pour les autres raisons suivantes :</span><span class="sxs-lookup"><span data-stu-id="2f8f8-177">Other reasons why we recommend bypassing the VPN:</span></span>
<ul>
<li><p><span data-ttu-id="2f8f8-178">Les VPN ne sont généralement pas conçus ou configurés pour prendre en charge les médias en temps réel.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-178">VPNs are typically not designed or configured to support real-time media.</span></span></p></li> 
<li><p><span data-ttu-id="2f8f8-179">Certains VPN peuvent également ne pas prendre en charge les UDP (obligatoires pour Teams).</span><span class="sxs-lookup"><span data-stu-id="2f8f8-179">Some VPNs might also not support UDP (which is required for Teams).</span></span></p></li> 
<li><p><span data-ttu-id="2f8f8-180">Les VPN offrent également une phase supplémentaire de chiffrement au-dessus du trafic multimédia déjà chiffré.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-180">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span></p></li> 
<li><p><span data-ttu-id="2f8f8-181">La connectivité à Teams peut ne pas être efficace en raison de l’épinglage de bande passante via un appareil VPN.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-181">Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.</span></span></p></li></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2f8f8-182">Mettre en œuvre la qualité de service (QoS)</span><span class="sxs-lookup"><span data-stu-id="2f8f8-182">Implement QoS</span></span></td>
<td><span data-ttu-id="2f8f8-183"><a href="/microsoftteams/qos-in-teams">Utilisez la qualité de service (QoS)</a> pour définir la priorité des paquets.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-183"><a href="/microsoftteams/qos-in-teams">Use Quality of Service (QoS)</a> to configure packet prioritization.</span></span> <span data-ttu-id="2f8f8-184">La qualité des appels dans Teams est améliorée et vous aide à surveiller la qualité des appels et à les résoudre.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-184">This will improve call quality in Teams and help you monitor and troubleshoot call quality.</span></span> <span data-ttu-id="2f8f8-185">QoS doit être implémenté sur tous les segments d’un réseau géré.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-185">QoS should be implemented on all segments of a managed network.</span></span> <span data-ttu-id="2f8f8-186">Même lorsqu’un réseau a été adéquatement mis en service pour la bande passante, QoS fournit une atténuation des risques en cas d’événements réseau inattendus.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-186">Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events.</span></span> <span data-ttu-id="2f8f8-187">Avec QoS, le trafic vocal est hiérarchisé de sorte que ces événements inattendus n’affectent pas la qualité.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-187">With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2f8f8-188">Optimisation du Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="2f8f8-188">Optimize WiFi</span></span></td>
<td><p><span data-ttu-id="2f8f8-189">Tout comme un réseau VPN, les réseaux Wi-Fi ne sont pas nécessairement conçus ou configurés pour prendre en charge les médias en temps réel.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-189">Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="2f8f8-190">La planification ou l’optimisation d’un réseau Wi-Fi pour prendre en charge Teams est un élément essentiel à prendre en considération pour un déploiement de haute qualité.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-190">Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment.</span></span> <span data-ttu-id="2f8f8-191">Tenez compte de ces facteurs :</span><span class="sxs-lookup"><span data-stu-id="2f8f8-191">Consider these factors:</span></span></p>
<ul>
<li><p><span data-ttu-id="2f8f8-192">Implémentez QoS ou WMM (Wi-Fi Multimedia) pour vous assurer que le trafic multimédia est hiérarchisé de façon appropriée sur vos réseaux Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-192">Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is getting prioritized appropriately over your WiFi networks.</span></span></p></li>
<li><p><span data-ttu-id="2f8f8-193">Planifiez et optimisez les bandes Wi-Fi et l’emplacement des points d’accès.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-193">Plan and optimize the WiFi bands and access point placement.</span></span> <span data-ttu-id="2f8f8-194">La gamme de 2,4 GHz peut fournir une expérience adéquate en fonction de l'emplacement des points d'accès, mais les points d'accès sont souvent affectés par d'autres appareils grand public qui fonctionnent dans cette gamme.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-194">The 2.4 GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="2f8f8-195">La gamme de 5 GHz est assez vaste et convient mieux aux éléments multimédias en temps réel, mais nécessite davantage de points d’accès pour obtenir une couverture suffisante.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-195">The 5 GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="2f8f8-196">Les points de terminaison doivent également prendre en charge cette bande et être configurés pour l’exploiter en conséquence.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-196">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span></p></li>
<li><p><span data-ttu-id="2f8f8-197">Si vous utilisez des réseaux WiFi à deux bandes, vous pouvez implémenter la direction de bandes.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-197">If you're using dual-band WiFi networks, consider implementing band steering.</span></span> <span data-ttu-id="2f8f8-198">La <em>direction de bande</em> est une technique implémentée par les fournisseurs Wi-Fi pour inciter les clients à bandes doubles afin d’utiliser la gamme de 5 GHz.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-198"><em>Band steering</em> is a technique implemented by WiFi vendors to influence dual-band clients to use the 5 GHz range.</span></span></p></li>
<li><p><span data-ttu-id="2f8f8-199">Lorsque les points d’accès d’un même canal sont trop proches les uns des autres, ils peuvent provoquer un chevauchement des signaux et une concurrence involontaire, ce qui peut nuire à l’expérience de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-199">When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="2f8f8-200">Veillez à ce que les points d'accès voisins se trouvent sur des canaux qui ne se superposent pas.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-200">Ensure that access points that are next to each other are on channels that don't overlap.</span></span></p></li>
</ul>
<p><span data-ttu-id="2f8f8-201">Chaque fournisseur de services sans fil a ses propres recommandations pour le déploiement de sa solution sans fil.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-201">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="2f8f8-202">Consultez votre fournisseur Wi-Fi pour obtenir des instructions spécifiques.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-202">Consult your WiFi vendor for specific guidance.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a><span data-ttu-id="2f8f8-203">Configuration de bande passante requise</span><span class="sxs-lookup"><span data-stu-id="2f8f8-203">Bandwidth requirements</span></span>

<span data-ttu-id="2f8f8-204">Teams est conçu pour offrir la meilleure expérience audio, vidéo et de partage de contenu, quelles que soient vos conditions réseau.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-204">Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="2f8f8-205">Cependant, lorsque la bande passante est insuffisante, Teams privilégie la qualité audio par rapport à la qualité vidéo.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-205">That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.</span></span>

<span data-ttu-id="2f8f8-206">Lorsque la bande passante n’est pas limitée, Teams optimise la qualité multimédia, y compris l’audio haute fidélité, la résolution vidéo jusqu’à 1 080p et jusqu’à 30 images (images par seconde) pour la vidéo et le contenu.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-206">Where bandwidth isn't limited, Teams optimizes media quality, including high-fidelity audio, up to 1080p video resolution, and up to 30fps (frames per second) for video and content.</span></span>

<span data-ttu-id="2f8f8-207">Le tableau suivant décrit la manière dont Teams utilise la bande passante.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-207">This table describes how Teams uses bandwidth.</span></span> <span data-ttu-id="2f8f8-208">Teams fait toujours preuve de prudence quant à l’utilisation de la bande passante et est en mesure de fournir une qualité vidéo HD en moins de 1,5 Mbits/s.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-208">Teams is always conservative on bandwidth utilization and can deliver HD video quality in under 1.5Mbps.</span></span> <span data-ttu-id="2f8f8-209">La consommation réelle de bande passante pour chaque appel ou réunion audio/vidéo varie en fonction de plusieurs facteurs, tels que la disposition vidéo, la résolution vidéo et les images vidéo par seconde.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-209">The actual bandwidth consumption in each audio/video call or meeting will vary based on several factors, such as video layout, video resolution, and video frames per second.</span></span> <span data-ttu-id="2f8f8-210">Lorsque la bande passante disponible est plus élevée, la qualité et l’utilisation s’améliorent pour offrir une expérience optimale.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-210">When more bandwidth is available, quality and usage will increase to deliver the best experience.</span></span>

:::row:::
   :::column span="":::
      <span data-ttu-id="2f8f8-211">**Modalité**</span><span class="sxs-lookup"><span data-stu-id="2f8f8-211">**Modality**</span></span>
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="2f8f8-212">**Exigences en bande passante (vitesse de transmission en Ko/s vers le haut/bas)**</span><span class="sxs-lookup"><span data-stu-id="2f8f8-212">**Bandwidth requirements (bitrate KB/s up/down)**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="2f8f8-213">**Minimum**</span><span class="sxs-lookup"><span data-stu-id="2f8f8-213">**Minimum**</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="2f8f8-214">**Recommandé**</span><span class="sxs-lookup"><span data-stu-id="2f8f8-214">**Recommended**</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="2f8f8-215">**Performances optimales**</span><span class="sxs-lookup"><span data-stu-id="2f8f8-215">**Best performance**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="2f8f8-216">**Audio**</span><span class="sxs-lookup"><span data-stu-id="2f8f8-216">**Audio**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="2f8f8-217">Un-à-un</span><span class="sxs-lookup"><span data-stu-id="2f8f8-217">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-218">10/10</span><span class="sxs-lookup"><span data-stu-id="2f8f8-218">10/10</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-219">58/58</span><span class="sxs-lookup"><span data-stu-id="2f8f8-219">58/58</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-220">76/76</span><span class="sxs-lookup"><span data-stu-id="2f8f8-220">76/76</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="2f8f8-221">Réunions</span><span class="sxs-lookup"><span data-stu-id="2f8f8-221">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-222">10/10</span><span class="sxs-lookup"><span data-stu-id="2f8f8-222">10/10</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-223">58/58</span><span class="sxs-lookup"><span data-stu-id="2f8f8-223">58/58</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-224">76/76</span><span class="sxs-lookup"><span data-stu-id="2f8f8-224">76/76</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="2f8f8-225">**Video**</span><span class="sxs-lookup"><span data-stu-id="2f8f8-225">**Video**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="2f8f8-226">Un-à-un</span><span class="sxs-lookup"><span data-stu-id="2f8f8-226">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-227">150/150</span><span class="sxs-lookup"><span data-stu-id="2f8f8-227">150/150</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-228">1 500/1 500</span><span class="sxs-lookup"><span data-stu-id="2f8f8-228">1,500/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-229">4 000/4 000</span><span class="sxs-lookup"><span data-stu-id="2f8f8-229">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="2f8f8-230">Réunions</span><span class="sxs-lookup"><span data-stu-id="2f8f8-230">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-231">150/200</span><span class="sxs-lookup"><span data-stu-id="2f8f8-231">150/200</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-232">2 500/4 000</span><span class="sxs-lookup"><span data-stu-id="2f8f8-232">2,500/4,000</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-233">4 000/4 000</span><span class="sxs-lookup"><span data-stu-id="2f8f8-233">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="2f8f8-234">**Partage d’écran**</span><span class="sxs-lookup"><span data-stu-id="2f8f8-234">**Screen sharing**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="2f8f8-235">Un-à-un</span><span class="sxs-lookup"><span data-stu-id="2f8f8-235">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-236">200/200</span><span class="sxs-lookup"><span data-stu-id="2f8f8-236">200/200</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-237">1 500/1 500</span><span class="sxs-lookup"><span data-stu-id="2f8f8-237">1,500/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-238">4 000/4 000</span><span class="sxs-lookup"><span data-stu-id="2f8f8-238">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="2f8f8-239">Réunions</span><span class="sxs-lookup"><span data-stu-id="2f8f8-239">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-240">250/250</span><span class="sxs-lookup"><span data-stu-id="2f8f8-240">250/250</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-241">2 500/2 500</span><span class="sxs-lookup"><span data-stu-id="2f8f8-241">2,500/2,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-242">4 000/4 000</span><span class="sxs-lookup"><span data-stu-id="2f8f8-242">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="2f8f8-243">**Mode Ensemble**</span><span class="sxs-lookup"><span data-stu-id="2f8f8-243">**Together Mode**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="2f8f8-244">Un-à-un</span><span class="sxs-lookup"><span data-stu-id="2f8f8-244">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-245">N/A</span><span class="sxs-lookup"><span data-stu-id="2f8f8-245">N/A</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-246">N/A</span><span class="sxs-lookup"><span data-stu-id="2f8f8-246">N/A</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-247">N/A</span><span class="sxs-lookup"><span data-stu-id="2f8f8-247">N/A</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="2f8f8-248">Réunions</span><span class="sxs-lookup"><span data-stu-id="2f8f8-248">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-249">1 000/1 500</span><span class="sxs-lookup"><span data-stu-id="2f8f8-249">1,000/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-250">1 500/2 500</span><span class="sxs-lookup"><span data-stu-id="2f8f8-250">1,500/2,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="2f8f8-251">2 500/4 000</span><span class="sxs-lookup"><span data-stu-id="2f8f8-251">2,500/4,000</span></span>
   :::column-end:::
:::row-end:::

<span data-ttu-id="2f8f8-252">**Les performances minimales**, **recommandées** et **optimales en matière** de bande passante sont basées sur l'utilisation par point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-252">**Minimum**, **Recommended**, and **Best performance** bandwidth requirements are based on per-endpoint usage.</span></span> <span data-ttu-id="2f8f8-253">En règle générale, il existe un point de terminaison par utilisateur, tel qu’un ordinateur ou un appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-253">Typically, there's one endpoint per user, such as a computer or mobile device.</span></span> <span data-ttu-id="2f8f8-254">Toutefois, si un utilisateur participe à une réunion Teams sur \*\* un ordinateur *et* un appareil mobile, deux points de terminaison sont associés à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-254">However, if a user joins a Teams meeting on *both* a computer *and* a mobile device, two endpoints are associated with that user.</span></span>

- <span data-ttu-id="2f8f8-255">Les exigences **minimales** en matière de bande passante pour les appels vidéo sont d’une résolution maximale de 240 p, de fréquences d’images de contenu de partage d’écran adaptatives de 1 875 à 7,5fps et de vidéo en mode ensemble/grande galerie jusqu’à une résolution de 540 p.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-255">**Minimum** Bandwidth requirements for video calls are up to 240p resolution, screen sharing content frame rates adaptive 1.875 to 7.5fps, and Together Mode/Large Gallery video up to 540p resolution.</span></span>  

- <span data-ttu-id="2f8f8-256">Les exigences **recommandées** en matière de bande passante pour les appels vidéo sont jusqu’à 1 080p de résolution<sup>\*</sup>, les fréquences d’images de contenu de partage d’écran s’adaptent de 7,5 à 30fps, et la vidéo en mode ensemble/grande galerie jusqu’à 1 080p de résolution<sup>\*</sup>.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-256">**Recommended** Bandwidth requirements for video calls are up to 1080p resolution<sup>\*</sup>, screen sharing content frame rates adaptive 7.5 to 30fps, and Together Mode/Large Gallery video up to 1080p resolution<sup>\*</sup>.</span></span>  

- <span data-ttu-id="2f8f8-257">**Meilleures performances** Les conseils offrent une meilleure fidélité vidéo pour les réunions de plus grands participants, des environnements à perte élevée et un contenu de mouvement plus élevé avec des fréquences d’images de contenu de partage d’écran adaptatives de 15 à 30fps.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-257">**Best Performance** Guidance allows higher fidelity video for larger attendee meetings, high loss environments, and higher motion content with screen sharing content frame rates adaptive 15 to 30fps.</span></span>

<span data-ttu-id="2f8f8-258"><sup>\*</sup>Attendez-vous à une qualité jusqu’à 1 080p, mais en fonction des conditions de votre réseau, la résolution et la qualité des vidéos seront optimisées en conséquence.</span><span class="sxs-lookup"><span data-stu-id="2f8f8-258"><sup>\*</sup>Expect up to 1080p quality but depending on your network conditions, video resolution and quality will be optimized accordingly.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="2f8f8-259">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2f8f8-259">Related Topics</span></span>

[<span data-ttu-id="2f8f8-260">Principes de connectivité réseau de Microsoft 365 et Office 365</span><span class="sxs-lookup"><span data-stu-id="2f8f8-260">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="2f8f8-261">Points de terminaison internationaux : Skype Entreprise Online et Teams</span><span class="sxs-lookup"><span data-stu-id="2f8f8-261">Worldwide endpoints: Skype for Business Online and Teams</span></span>](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[<span data-ttu-id="2f8f8-262">Serveurs proxy pour Teams</span><span class="sxs-lookup"><span data-stu-id="2f8f8-262">Proxy servers for Teams</span></span>](proxy-servers-for-skype-for-business-online.md)

[<span data-ttu-id="2f8f8-263">Médias dans Teams : pourquoi les réunions sont-elles simples ?</span><span class="sxs-lookup"><span data-stu-id="2f8f8-263">Media in Teams: Why meetings are simple</span></span>](https://aka.ms/teams-media)

[<span data-ttu-id="2f8f8-264">Médias dans Teams : les flux multimédias en profondeur</span><span class="sxs-lookup"><span data-stu-id="2f8f8-264">Media in Teams: Deep dive into media flows</span></span>](https://aka.ms/teams-media-flows)

[<span data-ttu-id="2f8f8-265">Modèles d’identité et authentification dans Teams</span><span class="sxs-lookup"><span data-stu-id="2f8f8-265">Identity models and authentication in Teams</span></span>](identify-models-authentication.md)

[<span data-ttu-id="2f8f8-266">Comment déployer Teams</span><span class="sxs-lookup"><span data-stu-id="2f8f8-266">How to roll out Teams</span></span>](./deploy-overview.md)

[<span data-ttu-id="2f8f8-267">Résolution des problèmes de Teams</span><span class="sxs-lookup"><span data-stu-id="2f8f8-267">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
