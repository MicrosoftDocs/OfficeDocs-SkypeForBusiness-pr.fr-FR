---
title: Vue d’ensemble du contrôle de stratégie pour Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Une vue d’ensemble des contrôles de stratégie pour Microsoft Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 13b807d98b92deaac54ad8b755295b73e90c6548
ms.sourcegitcommit: b4bc3b4c1d167a075a25180818f61758eb56cd6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2021
ms.locfileid: "61041256"
---
# <a name="policy-control-overview-for-microsoft-teams"></a>Vue d’ensemble du contrôle de stratégie pour Microsoft Teams

Microsoft s’engage à vous fournir les informations et les contrôles dont vous avez besoin pour effectuer des choix sur la façon dont vos données sont collectées et utilisées lorsque vous utilisez Microsoft Teams, une partie intégrante de Microsoft 365.

Cet article a pour but de vous fournir des informations sur les contrôles de confidentialité dans les domaines suivants :

- Les **données de diagnostic** collectées et envoyées à Microsoft pour communiquer des informations sur les logiciels Teams et Office, qui sont utilisés sur les ordinateurs fonctionnant sous Windows dans votre organisation.
- Les **expériences utilisateur connectées**, qui utilisent les fonctionnalités basées sur le cloud, pour fournir des fonctionnalités Teams et Office améliorées pour vous et vos utilisateurs.

Dans le cadre de ces modifications, vous remarquerez des nouveautés et des améliorations pour les éléments de l’interface utilisateur et les paramètres de stratégie

> [!IMPORTANT]
> Pour plus d’informations, consultez [Vue d’ensemble de contrôles de confidentialité pour Microsoft 365 Apps for enterprise](/deployoffice/privacy/overview-privacy-controls).

## <a name="diagnostic-data-sent-from-microsoft-365-apps-for-enterprise-to-microsoft"></a>Données de diagnostic envoyées à Microsoft par Microsoft 365 Apps for enterprise.

Les données de diagnostic sont utilisées pour :

- assurer la sécurité et la mise à jour de Teams.
- Détecter, diagnostiquer et résoudre les problèmes.
- apporter des améliorations au produit.

Voici des exemples de certaines données collectées :

- Langue de l’application
- Type d’utilisateur
- Version de build du système d’exploitation

## <a name="clients-that-adhere-to-diagnostic-controls"></a>Clients qui adhèrent aux contrôles de diagnostic

Les clients suivants adhèrent aux contrôles de diagnostic et soumettront des données :

- iOS
- Android
- Bureau (uniquement le composant qui utilise l’API win32)

Pour afficher la liste des événements de données de diagnostic requis et leurs propriétés, consultez les articles suivants :

- [Données de diagnostic de mobiles requises pour Microsoft Teams](policy-control-diagnostic-data-mobile.md)
- [Données de diagnostic de bureau requises pour Microsoft Teams](policy-control-diagnostic-data-desktop.md)

## <a name="diagnostic-data-sent-from-the-teams-app-to-microsoft"></a>Données de diagnostic envoyées à Microsoft par l’application Teams

Les données de diagnostic sont collectées et envoyées à Microsoft pour communiquer des informations sur le logiciel Teams, utilisé sur des ordinateurs fonctionnant sous Windows dans votre organisation.

Vous pouvez choisir parmi trois niveaux de données de diagnostic pour le logiciel Teams :

- **Requises** Les données minimales nécessaires pour garantir la sécurité, la mise à jour et les performances d’Office sur l’appareil sur lequel il est installé.
- **Facultatives** Des données supplémentaires qui nous permettent d’améliorer les produits et qui fournissent des informations enrichies pour nous aider à détecter, diagnostiquer et résoudre les problèmes.
- **Aucune** Aucune donnée de diagnostic concernant le logiciel Teams en cours d’exécution sur l’appareil de l’utilisateur n’est collectée ni envoyée. Toutefois, cette option limite considérablement notre capacité à détecter, diagnostiquer et résoudre les problèmes que vos utilisateurs peuvent rencontrer lors de leur utilisation de Teams.

Les données de diagnostic requises peuvent inclure, par exemple, des informations sur la version de Teams installée sur l’appareil ou inclure des informations qui indiquent que l’application Teams se ferme lorsque vous tentez de rejoindre une réunion. Les données de diagnostic facultatives peuvent inclure des informations sur le temps nécessaire pour passer un appel téléphonique, ce qui peut indiquer un problème de connectivité ou de performances du réseau.

Si vous choisissez d’envoyer des données de diagnostic facultatives, les données de diagnostic requises sont également incluses.

En tant qu’administrateur pour votre organisation, vous serez en mesure d’utiliser une paramètre de stratégie pour déterminer le niveau des données de diagnostic qui sont envoyées. Les données de diagnostic facultatives seront envoyées à Microsoft, sauf si vous modifiez le paramètre. Fournir des données de diagnostic facultatives permet à l’équipe d’ingénierie Office de Microsoft de détecter, diagnostiquer et atténuer les problèmes pour réduire leur impact sur votre organisation. 

Pour choisir le niveau de données de diagnostic qui nous est envoyé, utilisez le [Service de stratégies cloud Office](/deployoffice/overview-office-cloud-policy-service) et configurez le *Configurer le niveau de données de diagnostic de logiciel client envoyées à Microsoft par Office* . Il s'agit du même paramètre de stratégie utilisé pour configurer le niveau des données de diagnostic envoyées par les autres applications Office (telles que Word, Excel et PowerPoint) fournies avec Microsoft 365 Apps for enterprise.

Vos utilisateurs ne pourront pas modifier le niveau de données de diagnostic de leurs appareils s’ils sont connectés à Teams avec leurs informations d’identification de l’organisation, parfois appelées compte professionnel ou scolaire.

Ces données de diagnostic n’incluent pas les noms des utilisateurs, leurs adresses e-mail ou tout autre contenu utilisateur, tel que les fichiers Office partagés dans Teams, un message de conversation envoyé dans Teams ou le texte d’un billet publié dans un canal Teams. Notre système crée un ID unique qui est associé aux données de diagnostic de vos utilisateurs. Lorsque nous recevons des données de diagnostic indiquant que l’application Teams a cessé de fonctionner 100 fois, cet ID unique nous permet de déterminer s’il s’agit d’un seul utilisateur qui a été bloqué 100 fois ou si ce sont 100 utilisateurs différents qui ont été bloqués chacun une fois. Nous n’utilisons pas cet ID unique pour identifier un utilisateur spécifique.

Pour afficher les données de diagnostic qui sont envoyées à Microsoft, vous pouvez utiliser la visionneuse de données de diagnostic que vous pouvez télécharger et installer gratuitement depuis le Microsoft Store. Pour plus d’informations, consultez [Utiliser la visionneuse de diagnostic de données avec Office](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855).

## <a name="required-service-data-for-connected-experiences"></a>Données de service requises pour les expériences utilisateur connectées

Les données de service requises sont des données qui permettent de fournir ces expériences connectées sur le cloud, tout en veillant à ce que celles-ci soient sécurisées et se déroulent comme prévu. Vous pouvez choisir de ne pas proposer cette fonctionnalité à vos utilisateurs, auquel cas ces informations ne seront pas fournies à Microsoft pour prendre en charge la fonctionnalité des expériences utilisateur connectées. Vous pouvez en savoir plus sur les [données de service requises](/deployoffice/privacy/required-service-data).

## <a name="essential-services-for-microsoft-teams"></a>Services essentiels pour Microsoft Teams

Il existe également un ensemble de services qui est indispensable au fonctionnement de Microsoft 365 Apps for enterprise et qui ne peut pas être désactivé. Par exemple, le service de gestion des licences qui confirme que vous êtes autorisé à utiliser les Applications Microsoft 365 pour les entreprises. Les données de service requises pour ces services sont collectées et envoyées à Microsoft, indépendamment des autres paramètres de stratégie que vous avez configurés.

Si vous souhaitez en savoir plus, consultez l’article [Services Essentiels pour Office](/deployoffice/privacy/essential-services).
