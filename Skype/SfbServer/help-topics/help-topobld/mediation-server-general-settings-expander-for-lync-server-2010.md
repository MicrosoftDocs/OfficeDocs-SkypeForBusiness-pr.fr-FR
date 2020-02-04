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
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Dans cette boîte de dialogue, vous pouvez modifier les propriétés des serveurs de médiation. Le côté gauche est un ensemble de liens rapides qui vous permettent d’utiliser les paramètres généraux, les paramètres de saut suivant et les paramètres de passerelle PSTN. Dans chaque section se trouvent les paramètres suivants :'
ms.openlocfilehash: d439698bf0e383f9c89fb749ef4cedc7ae253997
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684547"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="9c476-105">Expandeur des paramètres généraux du serveur de médiation pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="9c476-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="9c476-106">Dans cette boîte de dialogue, vous pouvez modifier les propriétés des serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="9c476-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="9c476-107">Le côté gauche est un ensemble de liens rapides qui vous permettent d’utiliser les paramètres généraux, les paramètres de saut suivant et les paramètres de passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="9c476-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="9c476-108">Dans chaque section se trouvent les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="9c476-108">In each section are the following settings:</span></span>

 <span data-ttu-id="9c476-109">Informations **générales**:</span><span class="sxs-lookup"><span data-stu-id="9c476-109">**General**:</span></span>

- <span data-ttu-id="9c476-110">Nom de domaine **complet**: vous modifiez le nom de domaine complet du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="9c476-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="9c476-111">**Associations**: activez la case à cocher **associer le pool Edge (pour les composants multimédias)** et sélectionnez un serveur de périphérie ou un pool de périphérie du serveur de médiation à utiliser comme chemin multimédia pour l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="9c476-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="9c476-112">**Tronçon suivant**:</span><span class="sxs-lookup"><span data-stu-id="9c476-112">**Next hop**:</span></span>

- <span data-ttu-id="9c476-113">**Sélection du saut suivant**: faites une sélection à partir d’une liste du serveur frontal ou du pool frontal à utiliser comme chemin d’accès du serveur de médiation à utiliser pour communiquer avec votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="9c476-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="9c476-114">**Passerelle RTC**:</span><span class="sxs-lookup"><span data-stu-id="9c476-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="9c476-115">**Passerelle RTC du serveur de médiation**:</span><span class="sxs-lookup"><span data-stu-id="9c476-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="9c476-116">**Ports d’écoute**: définissez les ports que le serveur de médiation va écouter.</span><span class="sxs-lookup"><span data-stu-id="9c476-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="9c476-117">Vous pouvez définir un port pour **TLS ou TLS** (Transport Layer Security), ou **TCP**ou protocole de contrôle de transport.</span><span class="sxs-lookup"><span data-stu-id="9c476-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="9c476-118">Pour que l’entrée de port du protocole TCP soit disponible, vous devez activer la case à cocher **activer le port TCP**.</span><span class="sxs-lookup"><span data-stu-id="9c476-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9c476-119">Reportez-vous à la documentation et aux paramètres de configuration de votre passerelle RTC (réseau téléphonique commuté) pour déterminer si vous devez activer et définir des valeurs de port TLS, TCP ou les deux.</span><span class="sxs-lookup"><span data-stu-id="9c476-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="9c476-120">TLS est un protocole plus sécurisé, qui utilise des certificats pour chiffrer le trafic entre le serveur de médiation et la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="9c476-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="9c476-121">Les passerelles RTC ne prennent pas en charge le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="9c476-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="9c476-122">Une liste des lignes SIP et des passerelles définies et configurées pour votre déploiement est répertoriée.</span><span class="sxs-lookup"><span data-stu-id="9c476-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="9c476-123">Si aucune entrée n’est présente, il n’y a aucune passerelle SIP ni aucune passerelle RTC configurée pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="9c476-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="9c476-124">Vous définissez et configurez des lignes et des passerelles sous **composants partagés** dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="9c476-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c476-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9c476-125">See also</span></span>

[<span data-ttu-id="9c476-126">Présentation du trunking SIP</span><span class="sxs-lookup"><span data-stu-id="9c476-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="9c476-127">Options de déploiement de la passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="9c476-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
