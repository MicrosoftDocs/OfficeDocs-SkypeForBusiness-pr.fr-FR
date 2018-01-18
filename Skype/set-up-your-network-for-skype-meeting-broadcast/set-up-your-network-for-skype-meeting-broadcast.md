---
title: "Configurer votre réseau de diffusion de réunion Skype"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: SMB
description: "Obtenir des informations sur la fonctionnalité de diffusion de réunion Skype de Skype pour entreprise en ligne qui vous permet de planifier, produire et diffusion ou une manifestation grand public en ligne jusqu'à 10 000 participants."
ms.openlocfilehash: 3e4afb09d6a65654af418e14cc124e3c78dc0e0c
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="4ace5-103">Configurer votre réseau de diffusion de réunion Skype</span><span class="sxs-lookup"><span data-stu-id="4ace5-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="4ace5-104">Une fois que vous [Activez diffusion de réunion Skype](enable-skype-meeting-broadcast.md) de diffusion de réunion Skype, vous devez configurer votre réseau.</span><span class="sxs-lookup"><span data-stu-id="4ace5-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="4ace5-105">Effectuez cette étape si vous souhaitez maintenir des conférences Web et autres émissions pour les personnes à l’extérieur de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="4ace5-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>
  
<span data-ttu-id="4ace5-106">Si vous n’êtes pas familiarisé avec la configuration de votre pare-feu, envisager d’engager un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) d’effectuer cette étape pour vous.</span><span class="sxs-lookup"><span data-stu-id="4ace5-106">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="4ace5-107">Pour ignorer cette étape et l’ajouter à la place une autre entreprise vous pouvez inviter les diffusions à votre fédération, suivez les étapes de [Autoriser les utilisateurs à contacter Skype externe pour les utilisateurs professionnels](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="4ace5-107">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>
  
## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="4ace5-108">Étape 1 : Configurer des domaines autorisés</span><span class="sxs-lookup"><span data-stu-id="4ace5-108">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="4ace5-109">Pour configurer des domaines autorisés, utilisez l' **une** des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="4ace5-109">Use **one** of the following methods to set up allowed domains:</span></span>
  
### 

 <span data-ttu-id="4ace5-110">**Méthode 1 : Utiliser le centre d’administration Office 365**</span><span class="sxs-lookup"><span data-stu-id="4ace5-110">**Method 1: Use the Office 365 admin center**</span></span>
  
1. <span data-ttu-id="4ace5-111">Visitez le **Centre d’administration Office 365** et dans la navigation de gauche, cliquez sur **paramètres** > **Services &amp; des compléments**, puis cliquez sur **Skype pour les entreprises**.</span><span class="sxs-lookup"><span data-stu-id="4ace5-111">Go to the **Office 365 admin center** and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>
    
2. <span data-ttu-id="4ace5-112">Dans la page **partage externe** sous **exceptions du domaine**, sélectionnez **tous les domaines sont bloqués à l’exception**et entrez les domaines suivants, séparés par une virgule (,) :</span><span class="sxs-lookup"><span data-stu-id="4ace5-112">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>
    
  - <span data-ttu-id="4ace5-113">noammeetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="4ace5-113">noammeetings.lync.com</span></span>
    
  - <span data-ttu-id="4ace5-114">emeameetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="4ace5-114">emeameetings.lync.com</span></span>
    
  - <span data-ttu-id="4ace5-115">apacmeetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="4ace5-115">apacmeetings.lync.com</span></span>
    
  - <span data-ttu-id="4ace5-116">Resources.Lync.com</span><span class="sxs-lookup"><span data-stu-id="4ace5-116">resources.lync.com</span></span>
    
3. <span data-ttu-id="4ace5-117">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="4ace5-117">Click **Save**.</span></span>
    
### 

 <span data-ttu-id="4ace5-118">**Méthode 2 : Utiliser Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4ace5-118">**Method 2: Use Windows PowerShell**</span></span>
  
- <span data-ttu-id="4ace5-119">Dans le **Menu Démarrer**, avec le bouton droit de **Windows PowerShell** , puis cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="4ace5-119">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="4ace5-120">Dans la fenêtre **Windows PowerShell** , tapez chaque ligne et appuyez sur ENTRÉE.</span><span class="sxs-lookup"><span data-stu-id="4ace5-120">In the **Windows PowerShell** window, type each line and press Enter.</span></span>
    
  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="4ace5-121">Étape 2 : Ajout de diffusion réunion Skype domaines, des URL et IP adresses</span><span class="sxs-lookup"><span data-stu-id="4ace5-121">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="4ace5-122">La deuxième étape du processus d’installation consiste à ajouter des domaines qui sont nécessaires et ensuite ajouter des adresses IP et des URL qui sont requis pour la diffusion de réunion Skype fonctionner.</span><span class="sxs-lookup"><span data-stu-id="4ace5-122">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>
  
- <span data-ttu-id="4ace5-123">**Ajouter le Skype requis pour les professionnels en ligne URL de point de terminaison et adresses IP voir celles qui sont requises** [ici](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span><span class="sxs-lookup"><span data-stu-id="4ace5-123">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required**[here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>
    
## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="4ace5-124">Configurer la diffusion de réunion Skype dans les organisations et les déploiements hybride</span><span class="sxs-lookup"><span data-stu-id="4ace5-124">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="4ace5-125">Si vous avez un Skype pour l’organisation d’entreprise en ligne et d’un déploiement sur site de Lync Server 2010, Microsoft Lync Server 2013 et Skype pour Business Server 2015 et avez des utilisateurs à la fois en ligne et sur site, les autres étapes d’installation dont vous aurez besoin de Outre celles ci-dessus pour activer votre organisation sur place communiquer avec Skype pour entreprise en ligne et d’autoriser tous les utilisateurs puissent créer et joindre une diffusion de réunion Skype.</span><span class="sxs-lookup"><span data-stu-id="4ace5-125">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all of your users to be able to create and join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="4ace5-126">Pour voir quelles sont ces exigences, consultez [configurer votre déploiement sur site de diffusion de réunion Skype](https://go.microsoft.com/fwlink/?LinkId=617070).</span><span class="sxs-lookup"><span data-stu-id="4ace5-126">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4ace5-127">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="4ace5-127">Related topics</span></span>

[<span data-ttu-id="4ace5-128">Activer la diffusion de réunion Skype</span><span class="sxs-lookup"><span data-stu-id="4ace5-128">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)
  
[<span data-ttu-id="4ace5-129">URL et plages d'adresses IP Office 365</span><span class="sxs-lookup"><span data-stu-id="4ace5-129">Office 365 URLs and IP address ranges</span></span>](http://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[<span data-ttu-id="4ace5-130">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4ace5-130">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

