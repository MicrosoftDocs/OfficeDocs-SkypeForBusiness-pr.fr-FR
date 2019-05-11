---
title: Expandeur des paramètres généraux du serveur de médiation pour Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Vous modifiez les propriétés des serveurs de médiation dans cette boîte de dialogue. Sur le côté gauche est un ensemble de liens rapides pour les paramètres pour les paramètres généraux, paramètres du tronçon suivant et les paramètres de la passerelle PSTN. Dans chaque section sont les paramètres suivants :'
ms.openlocfilehash: ed4ed6c1c480417850bbfe194702a04b9e3af75f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888456"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="c6f37-105">Expandeur des paramètres généraux du serveur de médiation pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="c6f37-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="c6f37-106">Vous modifiez les propriétés des serveurs de médiation dans cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="c6f37-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="c6f37-107">Sur le côté gauche est un ensemble de liens rapides pour les paramètres pour les paramètres généraux, paramètres du tronçon suivant et les paramètres de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="c6f37-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="c6f37-108">Dans chaque section sont les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="c6f37-108">In each section are the following settings:</span></span>

 <span data-ttu-id="c6f37-109">**Général**:</span><span class="sxs-lookup"><span data-stu-id="c6f37-109">**General**:</span></span>

- <span data-ttu-id="c6f37-110">**Nom de domaine complet**: vous modifiez le nom de domaine complet du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="c6f37-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="c6f37-111">**Associations**: activez la case à cocher **pool Edge associé (pour les composants médias)** et sélectionnez un serveur Edge ou pool de serveurs Edge pour le serveur de médiation à utiliser en tant que le chemin d’accès des médias pour l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="c6f37-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="c6f37-112">**Tronçon suivant**:</span><span class="sxs-lookup"><span data-stu-id="c6f37-112">**Next hop**:</span></span>

- <span data-ttu-id="c6f37-113">**Sélection du tronçon suivant**: sélectionnez dans la liste le pool frontal ou serveur frontal à utiliser en tant que le chemin d’accès du serveur de médiation à utiliser pour communiquer avec votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="c6f37-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="c6f37-114">**Passerelle PSTN**:</span><span class="sxs-lookup"><span data-stu-id="c6f37-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="c6f37-115">**Passerelle PSTN de serveur de médiation**:</span><span class="sxs-lookup"><span data-stu-id="c6f37-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="c6f37-116">**Ports d’écoute**: définir les ports d’écoute sur le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="c6f37-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="c6f37-117">Vous pouvez définir un port pour **TLS** ou transport layer security, ou **TCP**, ou le protocole de transport.</span><span class="sxs-lookup"><span data-stu-id="c6f37-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="c6f37-118">Pour l’entrée de port TCP soit disponible, vous devez sélectionner la case à cocher pour **le port TCP activer**.</span><span class="sxs-lookup"><span data-stu-id="c6f37-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c6f37-119">Consultez les paramètres de configuration et de la documentation de votre passerelle de réseau téléphonique commuté pour déterminer si vous souhaitez activer et définir les valeurs de ports TLS, TCP ou les deux.</span><span class="sxs-lookup"><span data-stu-id="c6f37-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="c6f37-120">TLS est un protocole plus sécurisé, l’utilisation de certificats pour chiffrer le trafic entre le serveur de médiation et la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="c6f37-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="c6f37-121">Pas toutes les passerelles PSTN prend en charge TLS.</span><span class="sxs-lookup"><span data-stu-id="c6f37-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="c6f37-122">Une liste de jonctions SIP et les passerelles qui sont définis et configurés pour votre déploiement est répertoriée.</span><span class="sxs-lookup"><span data-stu-id="c6f37-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="c6f37-123">Si aucune entrée n’est présent, il n’existe aucune jonctions SIP ou des passerelles PSTN configurés pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="c6f37-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="c6f37-124">Vous définissez et configurez des jonctions et des passerelles sous **Composants partagés** dans le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="c6f37-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="c6f37-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c6f37-125">See also</span></span>

[<span data-ttu-id="c6f37-126">Vue d’ensemble d’une jonction SIP</span><span class="sxs-lookup"><span data-stu-id="c6f37-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="c6f37-127">Options de déploiement de passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="c6f37-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
