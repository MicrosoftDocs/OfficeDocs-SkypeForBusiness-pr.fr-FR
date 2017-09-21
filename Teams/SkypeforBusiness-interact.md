---
title: "Interaction entre Skype Entreprise et Microsoft Teams | Support Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: overview
ms.service: msteams
description: "Découvrez les modes d'interaction entre Skype Entreprise et Microsoft Teams, des conversations aux appels."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 02d11632a0a6b8f78504ab20ae3415a942e6c91f
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/20/2017
---
<a name="how-skype-for-business-and-microsoft-teams-interact"></a>Interaction entre Skype Entreprise et Microsoft Teams
===================================================

Si votre organisation utilise actuellement Skype Entreprise, il est important de comprendre l'interaction entre Skype Entreprise et Microsoft Teams.

Dans la disponibilité générale de Microsoft Teams, l'interopérabilité de base entre Microsoft Teams et Skype Entreprise Online ou déploiement hybride est disponible pour la messagerie instantanée P2P uniquement.

Le comportement par défaut consiste à ce que le client Microsoft Teams se connecte à la fois aux services principaux et aux services Skype Entreprise (méthode à double pile). Le client Microsoft Teams présentera uniquement les fonctionnalités de messagerie instantanée à Skype Entreprise ; ainsi la recherche d'un utilisateur Microsoft Teams dans Skype Entreprise affichera l'utilisateur dans la messagerie instantanée uniquement. Dans l'exemple illustré ci-après, Alix Wilber est uniquement connecté au client Microsoft Teams.

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image1.png)

Dans Microsoft Teams, les utilisateurs peuvent rechercher d'autres contacts dans leur organisation pour lesquels Skype Entreprise est activé et ouvrir des sessions de conversation par messagerie instantanée.

Dans Skype Entreprise, les utilisateurs peuvent répondre aux messages instantanés qui apparaîtront dans une fenêtre de conversation Microsoft Teams.

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image2.png)

Si Skype Entreprise est également activé pour les utillisateurs dans Microsoft Teams, ils peuvent se connecter à Microsoft Teams et Skype Entreprise à l'aide de leurs propres clients respectifs à la fois.

Le dernier point de terminaison actif sera retenu, ainsi si l'utilisateur utilise activement Microsoft Teams, les messages instantanés envoyés par un utilisateur Skype Entreprise s'afficheront dans la fenêtre de conversation Microsoft Teams. Si l'utilisateur utilise actuellement Skype Entreprise pour recevoir ou passer des appels, ou vient de répondre à un appel avec Skype Entreprise et qu'il n'est pas revenu sur le client Microsoft Teams, les messages instantanés envoyés par un utilisateur Skype Entreprise s'afficheront dans le client Skype Entreprise, car il s'agira du dernier point de terminaison actif.

Microsoft Teams prenant uniquement en charge l'interopérabilité de messagerie instantanée P2P avec Skype Entreprise actuellement, les appels audio/vidéo et les invitations à participer à des réunions Skype Entreprise provenant d'autres utilisateurs Skype Entreprise s'afficheront dans le client Skype Entreprise uniquement, dans tous les cas de figure. À l'inverse, les appels audio/vidéo et les invitations aux appels de groupe provenant du client Microsoft Teams, s'afficheront dans le client Microsoft Teams uniquement, dans tous les cas de figure.

Le comportement décrit plus haut permet aux utilisateurs finaux d'utiliser aisément Microsoft Teams et Skype Entreprise à la fois, et de gérer les besoins en communication spécifiques avec l'outil approprié. Toutefois, ils peuvent nécessiter des informations spécifiques pour comprendre le fonctionnement de l'interopérabilité et son impact sur l'expérience des utilisateurs finaux.


|  |  |
|---------|---------|
|![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image3.png)<br>Remarque</br>      |Avec l'interopérabilité de Skype Entreprise, les messages instantanés qui s'affichent dans Teams ne seront pas enregistrés dans l'historique des conversations de Skype Entreprise.         |

Microsoft Teams permet aux utilisateurs de désactiver l'interopérabilité de Skype Entreprise dans les paramètres de notification. Ce paramètre est contrôlé par l'utilisateur, et permet à chacun de décider du comportement qu'il souhaite appliquer.
