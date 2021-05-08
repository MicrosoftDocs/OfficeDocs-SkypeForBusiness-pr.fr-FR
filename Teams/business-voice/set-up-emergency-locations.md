---
title: Configurer des emplacements Microsoft 365 Business d’urgence voix
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Découvrez comment configurer des emplacements d’urgence pour Microsoft 365 Business Voix.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9fab5fead952837e2fb272819a600381252bcbf8
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282531"
---
# <a name="step-1-set-up-a-business-voice-emergency-location"></a><span data-ttu-id="f651d-103">Étape 1 : configurer un emplacement d’urgence Business Voice</span><span class="sxs-lookup"><span data-stu-id="f651d-103">Step 1: Set up a Business Voice emergency location</span></span>

<span data-ttu-id="f651d-104">Un emplacement d’urgence est utilisé lorsque quelqu’un dans votre organisation appelle des services d’urgence tels qu’un pare-feu, une police ou un numéro de police.</span><span class="sxs-lookup"><span data-stu-id="f651d-104">An emergency location is used when someone in your organization calls emergency services such as fire, police, or ambulance.</span></span> <span data-ttu-id="f651d-105">Lorsqu’une personne appelle un service d’urgence, l’adresse configurée comme adresse d’urgence de votre organisation est envoyée au service.</span><span class="sxs-lookup"><span data-stu-id="f651d-105">When a person calls an emergency service, the address that's configured as your organization's emergency address is sent to the service.</span></span> <span data-ttu-id="f651d-106">Cette étape définit l’emplacement d’urgence principal pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f651d-106">This step sets up the primary emergency location for your organization.</span></span> <span data-ttu-id="f651d-107">Cet emplacement sera associé au numéro de téléphone principal de votre société dans une étape ultérieure.</span><span class="sxs-lookup"><span data-stu-id="f651d-107">This location will be associated with your company's main phone number in a later step.</span></span>

<span data-ttu-id="f651d-108">Si vous avez des utilisateurs situés dans plusieurs emplacements, par exemple, des bureaux à domicile ou dans d’autres villes, vous pouvez configurer des emplacements d’urgence supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="f651d-108">If you have users in multiple locations, such as home offices or offices in other cities, you can configure additional emergency locations.</span></span> <span data-ttu-id="f651d-109">Vous pouvez même configurer des emplacements spécifiques au sein d’un emplacement.</span><span class="sxs-lookup"><span data-stu-id="f651d-109">You can even configure specific places within a location.</span></span> <span data-ttu-id="f651d-110">Les lieux peuvent être des bâtiments, des étages, des bureaux ou d’autres lieux où des utilisateurs peuvent se trouver dans un emplacement.</span><span class="sxs-lookup"><span data-stu-id="f651d-110">Places can be different buildings, floors, offices, or other places where users may be at a location.</span></span> <span data-ttu-id="f651d-111">D’autres emplacements et emplacements peuvent être ajoutés une fois que vous avez terminé la configuration initiale de Business Voice.</span><span class="sxs-lookup"><span data-stu-id="f651d-111">Additional locations and places can be added after you complete your initial setup of Business Voice.</span></span>

## <a name="add-an-emergency-location"></a><span data-ttu-id="f651d-112">Ajouter un emplacement d’urgence</span><span class="sxs-lookup"><span data-stu-id="f651d-112">Add an emergency location</span></span>

1. <span data-ttu-id="f651d-113">Ouvrez le Microsoft Teams d’administration et connectez-vous avec un utilisateur en tant qu’administrateur général (il s’agit généralement du compte que vous avez utilisé pour vous inscrire à Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="f651d-113">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="f651d-114">Dans le volet de navigation gauche, allez à <a href="https://admin.teams.microsoft.com/locations" target="_blank"> **Adresses d’urgence**  >  **d’emplacements.**</a></span><span class="sxs-lookup"><span data-stu-id="f651d-114">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/locations" target="_blank">**Locations** > **Emergency addresses**</a>.</span></span>
1. <span data-ttu-id="f651d-115">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f651d-115">Click **Add**.</span></span>
1. <span data-ttu-id="f651d-116">Entrez un nom et une description pour l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="f651d-116">Enter a name and description for the location.</span></span>
1. <span data-ttu-id="f651d-117">Sélectionnez le pays ou la région, puis entrez l’adresse.</span><span class="sxs-lookup"><span data-stu-id="f651d-117">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f651d-118">En Belgique, en France, en Allemagne, en Irlande, aux Pays-Bas et en Espagne, il est important de comprendre que, pour activer correctement un numéro de téléphone à Microsoft 365 ou Office 365, l’adresse définie dans l’emplacement d’urgence, qui est utilisé pour acquérir le numéro, doit correspondre à l’code de la zone du numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="f651d-118">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that to successfully activate a phone number in Microsoft 365 or Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number's area code.</span></span>

1. <span data-ttu-id="f651d-119">Si l’adresse est in trouvée et que vous voulez la modifier manuellement, vous pouvez activer modifier l’adresse **manuellement.**</span><span class="sxs-lookup"><span data-stu-id="f651d-119">If the address isn't found and you want to manually edit the address, turn on **Edit the address manually**.</span></span>
1. <span data-ttu-id="f651d-120">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f651d-120">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f651d-121">Étape suivante : configurer les numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="f651d-121">Next step: Set up phone numbers</span></span>](set-up-phone-numbers.md)
