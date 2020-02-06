---
title: Expandeur des paramètres généraux du serveur de médiation pour Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Dans cette boîte de dialogue, vous pouvez modifier les propriétés des serveurs de médiation. Le côté gauche est un ensemble de liens rapides qui vous permettent d’utiliser les paramètres généraux, les paramètres de saut suivant et les paramètres de passerelle PSTN. Dans chaque section se trouvent les paramètres suivants :'
ms.openlocfilehash: 3f7dad61778f54fee7a9be984191bc21f5029502
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819616"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="54c99-105">Expandeur des paramètres généraux du serveur de médiation pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="54c99-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="54c99-106">Dans cette boîte de dialogue, vous pouvez modifier les propriétés des serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="54c99-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="54c99-107">Le côté gauche est un ensemble de liens rapides qui vous permettent d’utiliser les paramètres généraux, les paramètres de saut suivant et les paramètres de passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="54c99-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="54c99-108">Dans chaque section se trouvent les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="54c99-108">In each section are the following settings:</span></span>

 <span data-ttu-id="54c99-109">Informations **générales**:</span><span class="sxs-lookup"><span data-stu-id="54c99-109">**General**:</span></span>

- <span data-ttu-id="54c99-110">Nom de domaine **complet**: vous modifiez le nom de domaine complet du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="54c99-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="54c99-111">**Associations**: activez la case à cocher **associer le pool Edge (pour les composants multimédias)** et sélectionnez un serveur de périphérie ou un pool de périphérie du serveur de médiation à utiliser comme chemin multimédia pour l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="54c99-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="54c99-112">**Tronçon suivant**:</span><span class="sxs-lookup"><span data-stu-id="54c99-112">**Next hop**:</span></span>

- <span data-ttu-id="54c99-113">**Sélection du saut suivant**: faites une sélection à partir d’une liste du serveur frontal ou du pool frontal à utiliser comme chemin d’accès du serveur de médiation à utiliser pour communiquer avec votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="54c99-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="54c99-114">**Passerelle RTC**:</span><span class="sxs-lookup"><span data-stu-id="54c99-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="54c99-115">**Passerelle RTC du serveur de médiation**:</span><span class="sxs-lookup"><span data-stu-id="54c99-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="54c99-116">**Ports d’écoute**: définissez les ports que le serveur de médiation va écouter.</span><span class="sxs-lookup"><span data-stu-id="54c99-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="54c99-117">Vous pouvez définir un port pour **TLS ou TLS** (Transport Layer Security), ou **TCP**ou protocole de contrôle de transport.</span><span class="sxs-lookup"><span data-stu-id="54c99-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="54c99-118">Pour que l’entrée de port du protocole TCP soit disponible, vous devez activer la case à cocher **activer le port TCP**.</span><span class="sxs-lookup"><span data-stu-id="54c99-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="54c99-119">Reportez-vous à la documentation et aux paramètres de configuration de votre passerelle RTC (réseau téléphonique commuté) pour déterminer si vous devez activer et définir des valeurs de port TLS, TCP ou les deux.</span><span class="sxs-lookup"><span data-stu-id="54c99-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="54c99-120">TLS est un protocole plus sécurisé, qui utilise des certificats pour chiffrer le trafic entre le serveur de médiation et la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="54c99-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="54c99-121">Les passerelles RTC ne prennent pas en charge le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="54c99-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="54c99-122">Une liste des lignes SIP et des passerelles définies et configurées pour votre déploiement est répertoriée.</span><span class="sxs-lookup"><span data-stu-id="54c99-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="54c99-123">Si aucune entrée n’est présente, il n’y a aucune passerelle SIP ni aucune passerelle RTC configurée pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="54c99-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="54c99-124">Vous définissez et configurez des lignes et des passerelles sous **composants partagés** dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="54c99-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="54c99-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="54c99-125">See also</span></span>

[<span data-ttu-id="54c99-126">Présentation du trunking SIP</span><span class="sxs-lookup"><span data-stu-id="54c99-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="54c99-127">Options de déploiement de la passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="54c99-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
