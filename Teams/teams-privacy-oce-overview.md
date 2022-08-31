---
title: Expériences connectées optionnelles dans Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: ''
ms.localizationpriority: high
search.appverid: MET150
description: Cet article décrit les expériences connectées optionnelles que vous connaîtrez dans Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03c23ccc1e9d24733f083c3e1d780b38138d366e
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396265"
---
# <a name="overview-of-optional-connected-experiences-in-microsoft-teams"></a>Vue d’ensemble des expériences connectées optionnelles dans Microsoft Teams

Si vous avez un compte professionnel ou scolaire, l’administrateur de votre organisation vous aura sans doute permis d’utiliser un ou plusieurs service(s) cloud soutenu(s) (également appelés **expériences connectées optionnelles**) lors de l’utilisation de Microsoft Teams. Exemples : GIPHY et/ou service d’aperçu d’URL. Ces services cloud sont facultatifs. Vous êtes libre de les utiliser ou non. Ils vous sont proposés sous des conditions différentes des conditions du [service Microsoft Online](https://www.microsoft.com/licensing/product-licensing/products), comme décrit séparément pour chaque service facultatif. Cet article répertorie les services cloud dans Teams.

Si votre administrateur vous a donné la possibilité d’utiliser des expériences connectées facultatives dans Teams, vous pouvez accéder à **Paramètres** > **Confidentialité** dans Teams et choisir d’utiliser des expériences connectées facultatives.

> [!NOTE]
> Si vous êtes administrateur, vous pouvez autoriser ou restreindre la possibilité pour vos utilisateurs d’utiliser des expériences connectées facultatives. Pour ce faire, vous pouvez utiliser le service de stratégies cloud [Office](/deployoffice/overview-office-cloud-policy-service) et configurer le *Autoriser l’utilisation d’expériences connectées facultatives supplémentaires dans le paramètre de stratégie* Office. Il s’agit du même paramètre de stratégie qui contrôle si les expériences connectées facultatives sont disponibles pour vos utilisateurs dans les applications Office (telles que Word, Excel et PowerPoint) fournies avec Microsoft 365 Apps for Entreprise.

## <a name="giphy"></a>GIPHY

GIPHY est un service cloud qui vous permet d’utiliser des images gif dans les conversations de vos équipes. Si vous êtes dans **La recherche** **GIF** >  **Teams** > , les termes de recherche sont envoyés à GIPHY. Votre administrateur doit d’abord autoriser ces expériences pour que vous puissiez les utiliser. Elles sont alors soumises à la [politique de confidentialité GIPHY](https://support.giphy.com/hc/articles/360032872931-GIPHY-Privacy-Policy) et aux [conditions d’utilisation du service](https://support.giphy.com/hc/articles/360020027752-GIPHY-User-Terms-of-Service).

:::image type="content" source="media/giphy-menu.png" alt-text="Ce menu affiche le bouton de sélection Giphy et la zone de saisie d’informations pour récupérer une ou plusieurs images Giphy.":::

## <a name="url-preview-service"></a>Service d’aperçu d’URL

Le service d’aperçu d’URL génère automatiquement un extrait de code d’aperçu et y joint la chaîne de l’URL envoyée par un utilisateur le cas échéant. Ce service envoie une requête à l’URL du service lorsque l’utilisateur tape le message. Si l’URL du service n’a pas de données schema.org, elle envoie une requête à la recherche Bing pour obtenir les données dont elle a besoin pour générer l’extrait de code en préversion. Les expériences qui reposent sur Bing sont concédées sous licence aux termes du [Contrat de services Microsoft](https://www.microsoft.com/servicesagreement) et couvertes par la [déclaration de confidentialité](https://privacy.microsoft.com/privacystatement). Toutes les URL que vous fournissez à Microsoft Teams lors de l’utilisation de ces services peuvent être envoyées à Microsoft Bing. Ils ne sont pas liés à vous par l’organisation Bing.

:::image type="content" source="media/url-preview.png" alt-text="Écran affichant un exemple d’aperçu d’URL pour la page d’accueil de Microsoft dans une zone de texte.":::

## <a name="teams-apps-link-previews"></a>Aperçus des liens d’applications Teams

Le service d’aperçu des liens d’application Teams génère un extrait de code d’aperçu de la carte adaptative de l’application et l’attache sous l’URL lorsqu’un utilisateur envoie une chaîne d’URL qui est mappée à l’application dans le Magasin Teams. Ce service envoie une requête à l’URL du service lorsque l’utilisateur tape le message.

## <a name="teams-device-store-checkout"></a>Extraction du magasin d’appareils Teams  

Le magasin d’appareils Teams se trouve dans le centre d’administration Teams et permet la découverte et l’achat d’appareils certifiés Teams. Pour activer l’extraction, le magasin d’appareils Teams partage des informations de base sur l’utilisateur et l’entreprise, notamment l’adresse e-mail de l’utilisateur, les GUID utilisateur et les GUID de locataire, avec UnifiedCommunications.com. Cette expérience, si elle est autorisée par autoriser **l’utilisation d’expériences connectées facultatives supplémentaires dans** le paramètre de stratégie Office , est soumise aux conditions d’utilisation et à la déclaration de confidentialité de UnifiedCommunications.com.

:::image type="content" source="media/teams-device-store-buttons.png" alt-text="Capture d’écran d’une partie de la page magasin d’appareils Teams avec les options de paiement fournies par UnifiedCommunications.com, une société tierce qui permet l’achat d’appareils auprès du Centre d’administration Teams.":::

Pour en savoir plus sur le magasin d’appareils Teams, consultez : [Acheter des appareils dans le magasin d’appareils Teams](devices/device-store.md)

## <a name="related-articles"></a>Articles connexes

- [Vue d’ensemble des contrôles de stratégie pour les équipes](policy-control-overview.md)
- [Confidentialité et Microsoft Teams](teams-privacy.md)
- [Expériences connectées supplémentaires pour Office](/deployoffice/privacy/optional-connected-experiences)
- [Données de service requises pour Office](/deployoffice/privacy/required-service-data)
- [Paramètres de confidentialité du compte](https://support.microsoft.com/office/3e7bc183-bf52-4fd0-8e6b-78978f7f121b)
