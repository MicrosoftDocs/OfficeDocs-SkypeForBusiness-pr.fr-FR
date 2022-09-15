---
title: Gérer les stratégies de réunion pour le partage de contenu
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.contentsharing
- seo-marvel-apr2020
description: Découvrez comment gérer les paramètres de stratégie de réunion dans Teams pour le partage de contenu.
ms.openlocfilehash: d3ae689ceb2c864f3f70da91728b8607aaa1e0e2
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706691"
---
# <a name="meeting-policy-settings---content-sharing"></a>Paramètres de stratégie de réunion : partage de contenu

<a name="bkcontentsharing"> </a>

Cet article décrit les paramètres de stratégie de réunion suivants liés au partage de contenu :

- [Mode de partage d’écran](#screen-sharing-mode)
- [Autoriser un participant à donner ou demander le contrôle](#allow-a-participant-to-give-or-request-control).
- [Les participants externes peuvent donner ou demander le contrôle](#external-participants-can-give-or-request-control)
- [PowerPoint Live](#powerpoint-live)
- [Tableau blanc](#whiteboard)
- [Notes partagées](#shared-notes)

## <a name="screen-sharing-mode"></a>Mode de partage d’écran

Ce paramètre est une combinaison de stratégies par organisateur et par utilisateur. Ce paramètre détermine si le partage de bureau et de fenêtre est autorisé dans la réunion de l’utilisateur. Les participants à la réunion qui n’ont pas de stratégies affectées (par exemple, les participants externes) héritent de la stratégie de l’organisateur de la réunion.

|Valeur du paramètre |Comportement  |
|---------|---------|
|**Écran entier**    | Le partage de bureau et le partage d’applications complets sont autorisés pendant la réunion. |
|**Application unique**   | Le partage d’applications est autorisé pendant la réunion        |
|**Désactivé**     |Partage d’écran et partage d’applications désactivé pendant la réunion.       |

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion |Mode de partage d’écran |
|---------|---------|---------|
|Daniela  | Global   | Écran entier |
|Geneviève   | Location1MeetingPolicy  | Désactivé |

Réunions hébergées par Daniela permettre aux participants d’une réunion de partager l’ensemble de l’écran ou d’une application spécifique. Si Amanda rejoint la réunion de Daniela, elle ne pourra pas partager son écran ou une application spécifique car son paramètre de stratégie est désactivé. Les réunions hébergées par Amanda ne sont pas autorisées à partager leur écran ou une seule application, quelle que soit la stratégie de mode de partage d’écran qui leur est attribuée.  Par conséquent, Daniela ne peut pas partager son écran ou une seule application dans les réunions d’Amanda.  

Pour l’instant, les utilisateurs ne peuvent pas lire de vidéo ou partager leur écran dans une réunion Teams s’ils utilisent Google Chrome.

## <a name="allow-a-participant-to-give-or-request-control"></a>Autoriser un participant à donner ou demander le contrôle

Ce paramètre est une stratégie par utilisateur. Ce paramètre détermine si l’utilisateur peut donner le contrôle de la fenêtre ou du Bureau partagé aux autres participants à la réunion. Pour donner le contrôle, pointez sur la partie supérieure de l’écran.

Si ce paramètre est activé pour l’utilisateur, l’option **Attribuer un contrôle** s’affiche dans la barre supérieure d’une session de partage.

![Capture d’écran montrant l’option Donner le contrôle.](media/meeting-policies-give-control.png)

Si le paramètre est désactivé pour l’utilisateur, l’option **Donner le contrôle** n’est pas disponible.

![Capture d’écran montrant que l’option Donner le contrôle n’est pas disponible.](media/meeting-policies-give-control-not-available.png)

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion  |Autoriser un participant à donner ou demander le contrôle |
|---------|---------|---------|
|Daniela   | Global   | Activé       |
|Babek    | Location1MeetingPolicy        | Désactivé   |

Daniela peut donner le contrôle du bureau partagé ou de la fenêtre à d’autres participants à une réunion organisée par Babek. Toutefois, Babek ne peut pas donner le contrôle aux autres participants.

Pour utiliser PowerShell afin de contrôler qui peut donner le contrôle ou accepter les demandes de contrôle, utilisez l’applet de commande AllowParticipantGiveRequestControl.

> [!NOTE]
> Pour donner et prendre le contrôle du contenu partagé pendant le partage, les deux personnes doivent utiliser le client de bureau Teams. Le contrôle n’est pas pris en charge lorsqu'une des parties exécute Teams dans un navigateur. Il s'agit d'une limitation technique que nous nous efforçons de résoudre.

## <a name="external-participants-can-give-or-request-control"></a>Les participants externes peuvent donner ou demander le contrôle

Ce paramètre est une stratégie par utilisateur. Le fait qu’une organisation ait défini cette stratégie pour un utilisateur ne contrôle pas ce que les participants externes peuvent faire, indépendamment de ce que l’organisateur de la réunion a défini. Ce paramètre détermine si les participants externes peuvent bénéficier d’un contrôle ou demander le contrôle de l’écran du destinataire, en fonction de ce que le partage a défini dans les stratégies de réunion de leur organisation. Les participants externes aux réunions Teams peuvent être classés comme suit :  

- Participant anonyme
- Invités
- Utilisateurs de l’accès externe

Si les utilisateurs d’accès externe peuvent donner le contrôle à d’autres participants externes pendant que le partage est contrôlé par les **participants externes peuvent donner ou demander le paramètre de contrôle** dans leur organisation.

Pour utiliser PowerShell afin de contrôler si les participants externes peuvent transmettre des demandes de contrôle ou d’acceptation, utilisez l’applet de commande AllowExternalParticipantGiveRequestControl.

### <a name="powerpoint-live"></a>PowerPoint Live

Il s’agit d’une stratégie par utilisateur. Ce paramètre détermine si l’utilisateur peut partager des diapositives PowerPoint dans une réunion. Les participants externes, y compris les utilisateurs anonymes, invités et externes, héritent de la stratégie de l’organisateur de la réunion.

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion  |PowerPoint Live |
|---------|---------|---------|
|Daniela   | Global   | Activé       |
|Geneviève   | Location1MeetingPolicy        | Désactivé   |

Amanda ne peut pas partager les diapositives PowerPoint dans les réunions, même si elle est l’organisatrice de la réunion. Daniela peut partager des diapositives PowerPoint, même si la réunion est organisée par Amanda. Amanda peut afficher les diapositives PowerPoint partagées par d’autres personnes pendant la réunion, même si elles ne peuvent pas partager les diapositives PowerPoint.

## <a name="whiteboard"></a>Tableau blanc

Ce paramètre est une stratégie par utilisateur. Ce paramètre détermine si un utilisateur peut partager le tableau blanc pendant une réunion. Les participants externes, y compris les utilisateurs anonymes, invités et externes, héritent de la stratégie de l’organisateur de la réunion.

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion  |Tableau blanc|
|---------|---------|---------|
|Daniela   | Global   | Activé       |
|Geneviève   | Location1MeetingPolicy        | Désactivé   |

Amanda ne peut pas partager le tableau blanc pendant une réunion, même si elle est l’organisatrice de la réunion. Daniela peut partager le tableau blanc même si une réunion est organisée par Amanda.

Pour activer le tableau blanc à l’aide de PowerShell, définissez l’applet de commande IsWBFluidEnabled sur $true à partir de [Set-SPOTenant.](/powershell/module/sharepoint-online/set-spotenant)

### <a name="annotation"></a>Annotation

Lorsque le tableau blanc est activé, vos utilisateurs ont la possibilité d’utiliser [l’annotation](/office/use-annotation-while-sharing-your-screen-in-teams), une fonctionnalité qui permet aux participants de collaborer tout en partageant leur écran dans une réunion Teams. Si le tableau blanc est désactivé, les utilisateurs n’auront pas accès à l’annotation.

## <a name="shared-notes"></a>Notes partagées

Ce paramètre est une stratégie par utilisateur. Ce paramètre détermine si un utilisateur peut créer et partager des notes pendant une réunion. Les participants externes, y compris les participants anonymes, les invités et l’accès externe, héritent de la stratégie de l’organisateur de la réunion. L’onglet **Notes de réunion** n’est pas pris en charge pour l’instant pour les réunions ayant moins de 20 participants.

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion  |Notes partagées |
|---------|---------|---------|
|Daniela   | Global   | Activé       |
|Geneviève   | Location1MeetingPolicy | Désactivé |

Daniela peut prendre des notes dans les réunions d’Amanda et Amanda ne peut pas prendre de notes pendant une réunion.




## <a name="related-topics"></a>Sujets associés

- [Présentation de Teams PowerShell](teams-powershell-overview.md)
- [Attribuer des stratégies à vos utilisateurs](policy-assignment-overview.md)
- [Supprimer la stratégie de réunion Teams RestrictedAnonymousAccess des utilisateurs](meeting-policies-restricted-anonymous-access.md)
