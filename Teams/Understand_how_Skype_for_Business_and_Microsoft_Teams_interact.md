---
title: "Interaction entre Skype Entreprise et Microsoft Teams | Support Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdar
ms.date: 08/11/2017
ms.topic: overview
ms.prod: teams
description: "Découvrez les modes d'interaction entre Skype Entreprise et Microsoft Teams, des conversations aux appels."
ms.openlocfilehash: cb459fa444f7324a358fbd325e3ddb5cfd4c1966
ms.sourcegitcommit: 3b9b3f07f4f67cd5f43da68f48d62222d7e49167
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/31/2017
---
<a name="how-skype-for-business-and-microsoft-teams-interact"></a><span data-ttu-id="a0550-103">Interaction entre Skype Entreprise et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a0550-103">How Skype for Business and Microsoft Teams interact</span></span>
===================================================

<span data-ttu-id="a0550-104">Si votre organisation utilise actuellement Skype Entreprise, il est important de comprendre l'interaction entre Skype Entreprise et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a0550-104">If your organization uses Skype for Business today, it is important to understand how Skype for Business and Microsoft Teams will interact.</span></span>

<span data-ttu-id="a0550-105">Dans la disponibilité générale de Microsoft Teams, l'interopérabilité de base entre Microsoft Teams et Skype Entreprise Online ou déploiement hybride est disponible pour la messagerie instantanée P2P uniquement.</span><span class="sxs-lookup"><span data-stu-id="a0550-105">At general availability of Microsoft Teams, basic interoperability between Microsoft Teams and Skype for Business Online or Hybrid is available peer to peer (P2P) instant messaging only.</span></span>

<span data-ttu-id="a0550-p101">Le comportement par défaut consiste à ce que le client Microsoft Teams se connecte à la fois aux services principaux et aux services Skype Entreprise (méthode à double pile). Le client Microsoft Teams présentera uniquement les fonctionnalités de messagerie instantanée à Skype Entreprise ; ainsi la recherche d'un utilisateur Microsoft Teams dans Skype Entreprise affichera l'utilisateur dans la messagerie instantanée uniquement. Dans l'exemple illustré ci-après, Alix Wilber est uniquement connecté au client Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a0550-p101">The default behavior is that the Microsoft Teams client will sign into both the Microsoft Teams backend services and the Skype for Business services (a dual-stack approach). The Microsoft Teams client will only present IM capabilities to Skype for Business, so looking up a Microsoft Teams user from Skype for Business will only indicate the user as IM Only – shown in the example below, Alix Wilber is only signed into the Microsoft Teams client.</span></span>

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image1.png)

<span data-ttu-id="a0550-108">Dans Microsoft Teams, les utilisateurs peuvent rechercher d'autres contacts dans leur organisation pour lesquels Skype Entreprise est activé et ouvrir des sessions de conversation par messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="a0550-108">From Microsoft Teams, users can search for other users within their organization who are currently only enabled for Skype for Business, and conduct instant messaging chat sessions.</span></span>

<span data-ttu-id="a0550-109">Dans Skype Entreprise, les utilisateurs peuvent répondre aux messages instantanés qui apparaîtront dans une fenêtre de conversation Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a0550-109">Users on Skype for Business can reply to the instant messages, which will arrive in Microsoft Teams’ chat window.</span></span>

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image2.png)

<span data-ttu-id="a0550-110">Si Skype Entreprise est également activé pour les utillisateurs dans Microsoft Teams, ils peuvent se connecter à Microsoft Teams et Skype Entreprise à l'aide de leurs propres clients respectifs à la fois.</span><span class="sxs-lookup"><span data-stu-id="a0550-110">Users on Microsoft Teams, if enabled for Skype for Business as well, can sign in to Microsoft Teams and Skype for Business using their own respective clients simultaneously.</span></span>

<span data-ttu-id="a0550-p102">Le dernier point de terminaison actif sera retenu, ainsi si l'utilisateur utilise activement Microsoft Teams, les messages instantanés envoyés par un utilisateur Skype Entreprise s'afficheront dans la fenêtre de conversation Microsoft Teams. Si l'utilisateur utilise actuellement Skype Entreprise pour recevoir ou passer des appels, ou vient de répondre à un appel avec Skype Entreprise et qu'il n'est pas revenu sur le client Microsoft Teams, les messages instantanés envoyés par un utilisateur Skype Entreprise s'afficheront dans le client Skype Entreprise, car il s'agira du dernier point de terminaison actif.</span><span class="sxs-lookup"><span data-stu-id="a0550-p102">The last active endpoint will be honored, so if the user is actively using Microsoft Teams, any instant messages sent from a Skype for Business user will arrive in the Microsoft Teams chat window. If the user is currently using Skype for Business to receive/make phone calls or just finished taking a call using Skype for Business, and have not returned to Microsoft Teams client, incoming instant messages sent from a Skype for Business user will arrive in Skype for Business client as this will be the most active endpoint.</span></span>

<span data-ttu-id="a0550-p103">Microsoft Teams prenant uniquement en charge l'interopérabilité de messagerie instantanée P2P avec Skype Entreprise actuellement, les appels audio/vidéo et les invitations à participer à des réunions Skype Entreprise provenant d'autres utilisateurs Skype Entreprise s'afficheront dans le client Skype Entreprise uniquement, dans tous les cas de figure. À l'inverse, les appels audio/vidéo et les invitations aux appels de groupe provenant du client Microsoft Teams, s'afficheront dans le client Microsoft Teams uniquement, dans tous les cas de figure.</span><span class="sxs-lookup"><span data-stu-id="a0550-p103">As Microsoft Teams only currently supports peer-to-peer (P2P) instant messaging interop between Skype for Business, any audio/video calls or invitation to join a Skype for Business meetings, for any modalities, from other Skype for Business users will arrive on the Skype for Business client only. In the reverse, any audio/video calls or invitation to join group calling, for any modalities from Microsoft Teams client, will only arrive on the Microsoft Teams client.</span></span>

<span data-ttu-id="a0550-p104">Le comportement décrit plus haut permet aux utilisateurs finaux d'utiliser aisément Microsoft Teams et Skype Entreprise à la fois, et de gérer les besoins en communication spécifiques avec l'outil approprié. Toutefois, ils peuvent nécessiter des informations spécifiques pour comprendre le fonctionnement de l'interopérabilité et son impact sur l'expérience des utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="a0550-p104">With the above behavior, end users can comfortably use both Microsoft Teams and Skype for Business at the same time, and handle specific communications needs using the right tool. However, proper end user awareness may be required to understand how interoperability works and how it may impact end user experience.</span></span>


|  |  |
|---------|---------|
|![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image3.png)<br><span data-ttu-id="a0550-117">Remarque</span><span class="sxs-lookup"><span data-stu-id="a0550-117">Note:</span></span></br>      |<span data-ttu-id="a0550-118">Avec l'interopérabilité de Skype Entreprise, les messages instantanés qui s'affichent dans Teams ne seront pas enregistrés dans l'historique des conversations de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="a0550-118">With Skype for Business interoperability, instant messages that arrive in Teams will not be recorded in Skype for Business conversation history.</span></span>         |

<span data-ttu-id="a0550-p105">Microsoft Teams permet aux utilisateurs de désactiver l'interopérabilité de Skype Entreprise dans les paramètres de notification. Ce paramètre est contrôlé par l'utilisateur, et permet à chacun de décider du comportement qu'il souhaite appliquer.</span><span class="sxs-lookup"><span data-stu-id="a0550-p105">Microsoft Teams provides the ability for users to disable Skype for Business interoperability from within the Notification settings. This setting is user controlled, allowing each user to decide on the behavior they prefer.</span></span>
