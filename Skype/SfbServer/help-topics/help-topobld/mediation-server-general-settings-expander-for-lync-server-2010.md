---
title: Développement de paramètres général de serveur de médiation pour Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Vous modifiez les propriétés des serveurs de médiation dans cette boîte de dialogue. Sur le côté gauche est un ensemble de liens rapides pour vous faire passer les paramètres pour les paramètres généraux, les paramètres de saut suivant et les paramètres de la passerelle RTPC. Dans chaque section sont les suivants :'
ms.openlocfilehash: bc5016c9dbeb6b0693444f930c9883b1736258d2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="cb766-105">Développement de paramètres général de serveur de médiation pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="cb766-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="cb766-106">Vous modifiez les propriétés des serveurs de médiation dans cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="cb766-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="cb766-107">Sur le côté gauche est un ensemble de liens rapides pour vous faire passer les paramètres pour les paramètres généraux, les paramètres de saut suivant et les paramètres de la passerelle RTPC.</span><span class="sxs-lookup"><span data-stu-id="cb766-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="cb766-108">Dans chaque section sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="cb766-108">In each section are the following settings:</span></span>
  
 <span data-ttu-id="cb766-109">**Général**:</span><span class="sxs-lookup"><span data-stu-id="cb766-109">**General**:</span></span>
  
- <span data-ttu-id="cb766-110">**Nom de domaine complet**: vous modifiez le nom de domaine pleinement qualifié du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="cb766-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>
    
- <span data-ttu-id="cb766-111">**Associations**: cochez la case **pool d’associer le bord (pour les composants de support)** , sélectionnez un serveur de transport Edge ou à un pool de bord pour le serveur de médiation à utiliser comme le chemin d’accès au support pour l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="cb766-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>
    
 <span data-ttu-id="cb766-112">**Tronçon suivant**:</span><span class="sxs-lookup"><span data-stu-id="cb766-112">**Next hop**:</span></span>
  
- <span data-ttu-id="cb766-113">**Sélection de saut suivante**: sélectionner dans une liste le pool Front-End ou de serveur frontal à utiliser en tant que le chemin d’accès pour le serveur de médiation à utiliser pour communiquer avec votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="cb766-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>
    
 <span data-ttu-id="cb766-114">**Passerelle PSTN**:</span><span class="sxs-lookup"><span data-stu-id="cb766-114">**PSTN gateway**:</span></span>
  
 <span data-ttu-id="cb766-115">**Passerelle PSTN de serveur de médiation**:</span><span class="sxs-lookup"><span data-stu-id="cb766-115">**Mediation Server PSTN gateway**:</span></span>
  
- <span data-ttu-id="cb766-116">**Ports d’écoute**: définir les ports qui écoute sur le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="cb766-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="cb766-117">Vous pouvez définir un port pour la sécurité de la couche transport ou **TLS** ou **TCP**, ou le protocole de contrôle de transport.</span><span class="sxs-lookup"><span data-stu-id="cb766-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="cb766-118">Pour l’entrée de port pour TCP soit disponible, vous devez sélectionner la case à cocher pour **Activer le TCP port**.</span><span class="sxs-lookup"><span data-stu-id="cb766-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="cb766-119">Reportez-vous à la documentation et configuration pour votre passerelle de réseau téléphonique public commuté pour déterminer si vous devez activer et définir les valeurs de port TLS, TCP ou les deux.</span><span class="sxs-lookup"><span data-stu-id="cb766-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="cb766-120">TLS est un protocole plus sécurisé, l’utilisation de certificats pour crypter le trafic entre le serveur de médiation et la passerelle RTC.</span><span class="sxs-lookup"><span data-stu-id="cb766-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="cb766-121">Les passerelles RTPC pas tous en charge TLS.</span><span class="sxs-lookup"><span data-stu-id="cb766-121">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="cb766-122">Une liste des puits SIP et les passerelles qui sont définis et configurés pour votre déploiement est répertoriée.</span><span class="sxs-lookup"><span data-stu-id="cb766-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="cb766-123">Si aucune entrée n’est présente, il n’y aucun SIP troncs ou des passerelles RTPC configurés pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="cb766-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="cb766-124">Vous définissez et configurez les trunks et passerelles sous **Composants partagés** dans le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="cb766-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cb766-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cb766-125">See also</span></span>

#### 

[<span data-ttu-id="cb766-126">Vue d’ensemble des SIP Trunking</span><span class="sxs-lookup"><span data-stu-id="cb766-126">Overview of SIP Trunking</span></span>](http://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)
  
[<span data-ttu-id="cb766-127">Options de déploiement de passerelle RTPC</span><span class="sxs-lookup"><span data-stu-id="cb766-127">PSTN Gateway Deployment Options</span></span>](http://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)

