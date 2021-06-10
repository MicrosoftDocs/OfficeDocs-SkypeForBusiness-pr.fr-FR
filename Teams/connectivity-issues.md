---
title: Résoudre les problèmes de connectivité avec Teams client
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Résoudre les problèmes de connectivité avec le client Microsoft Teams, principalement causés par le pare-feu ou la connexion proxy, et découvrir comment résoudre ce problème.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f9ef787a5e103649c1526fab321cc8a9a088254c
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856163"
---
# <a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="faebd-103">Résoudre les problèmes de connectivité avec le client Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="faebd-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>

<span data-ttu-id="faebd-104">La plupart des problèmes détectés avec le client Microsoft Teams peuvent être attribués au pare-feu ou à la connectivité du proxy.</span><span class="sxs-lookup"><span data-stu-id="faebd-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="faebd-105">Vérifier que les URL, les adresses IP et les ports nécessaires sont ouverts dans votre pare-feu ou votre proxy réduit le nombre de dépannages inutiles.</span><span class="sxs-lookup"><span data-stu-id="faebd-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="faebd-106">Pour obtenir des informations spécifiques sur les URL et adresses IP requises pour Microsoft Teams, consultez l’article Microsoft 365 et Office 365 de prise en charge des [adresses IP.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)</span><span class="sxs-lookup"><span data-stu-id="faebd-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="faebd-107">Les cas suivants nécessitent l'ouverture d'URL et de ports spécifiques dans le pare-feu.</span><span class="sxs-lookup"><span data-stu-id="faebd-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

- <span data-ttu-id="faebd-108">Authentification</span><span class="sxs-lookup"><span data-stu-id="faebd-108">Authentication</span></span>

- <span data-ttu-id="faebd-109">Connectivité du client Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="faebd-109">Microsoft Teams Client Connectivity</span></span>

- <span data-ttu-id="faebd-110">Collaboration</span><span class="sxs-lookup"><span data-stu-id="faebd-110">Collaboration</span></span>

- <span data-ttu-id="faebd-111">Multimédia</span><span class="sxs-lookup"><span data-stu-id="faebd-111">Media</span></span>

- <span data-ttu-id="faebd-112">Services partagés</span><span class="sxs-lookup"><span data-stu-id="faebd-112">Shared Services</span></span>

- <span data-ttu-id="faebd-113">Intégration de tiers</span><span class="sxs-lookup"><span data-stu-id="faebd-113">Third Party Integration</span></span>

- <span data-ttu-id="faebd-114">Interopérabilité de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="faebd-114">Skype for Business Interoperability</span></span>

- <span data-ttu-id="faebd-115">Interopérabilité du client Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="faebd-115">Skype for Business Client Interoperability</span></span>

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a><span data-ttu-id="faebd-116">Lorsque Teams est hors connexion ou dans des conditions de faible bande passante</span><span class="sxs-lookup"><span data-stu-id="faebd-116">When Teams is offline or in low bandwidth conditions</span></span>

<span data-ttu-id="faebd-117">La bonne nouvelle, c’est Teams s’exécute sans cesse même lorsque vous êtes hors connexion ou dans des conditions de faible bande passante.</span><span class="sxs-lookup"><span data-stu-id="faebd-117">The good news is that Teams keeps running even when you're offline or running in low bandwidth conditions.</span></span> <span data-ttu-id="faebd-118">Teams enregistre tous vos messages non envoyés pour les conversations existantes (pendant 24 heures) et les envoie dès que vous vous remettreez en ligne.</span><span class="sxs-lookup"><span data-stu-id="faebd-118">Teams saves all your unsent messages for existing chats (for up to 24 hours) and sends them as soon as you're back online.</span></span> <span data-ttu-id="faebd-119">Si vous êtes hors connexion pendant plus de 24 heures, Teams vous permet de renvoyer ou de supprimer les messages non envoyés.</span><span class="sxs-lookup"><span data-stu-id="faebd-119">If you're offline for longer than 24 hours, Teams lets you choose to resend or delete unsent messages.</span></span> <span data-ttu-id="faebd-120">Nous travaillons à l’ajout de cette fonctionnalité aux nouvelles conversations et nous actualiserons cette documentation lorsqu’elle sera disponible.</span><span class="sxs-lookup"><span data-stu-id="faebd-120">We're working on adding this functionality to new chats and will update this documentation when that's available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="faebd-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="faebd-121">Related topics</span></span>

[<span data-ttu-id="faebd-122">Résolution des problèmes de Teams</span><span class="sxs-lookup"><span data-stu-id="faebd-122">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)