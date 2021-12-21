---
title: Planifier votre déploiement pour les Teams téléphones et les affichages
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: tony.woodruff
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
search.appverid: MET150
description: Cet article fournit une vue d’ensemble des tâches et étapes de déploiement Teams téléphones et affichages dans votre organisation.
ms.openlocfilehash: 2ad9840d6ebd1ac6973027dedf6be294704f5326
ms.sourcegitcommit: 73d12d90fc20e3d943301f57ee434379d0b0e91b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2021
ms.locfileid: "61577794"
---
# <a name="plan-your-deployment-for-teams-phone-devices-and-displays"></a>Planifier votre déploiement pour les Teams téléphones et les affichages

Le déploiement réussi d’appareils Teams et d’affichages Teams démarre par une planification. Cet article vous permettra de suivre les tâches et étapes de déploiement de ces appareils dans votre organisation. Il fournit également des conseils sur l’utilisation des appareils, les licences, l’intégration à votre environnement, les points tactiles et la gestion.

> [!TIP]
> [Le Microsoft 365'Adoption Hub d’adoption](https://adoption.microsoft.com/) constitue un excellent pas dans le processus d’adoption avec Microsoft Teams.

## <a name="task-1-what-are-your-deployment-objectives"></a>Tâche 1 : quels sont vos objectifs de déploiement ?

La planification du déploiement de Teams et des affichages dans votre organisation commence par vos objectifs de déploiement. Teams appareils hybrides peuvent être utilisés dans des salles de réunion, des bureaux et d’autres espaces fonctionnels. Vous devrez déterminer où ces appareils seront utilisés et par qui.

### <a name="objective-identify-your-device-personas"></a>Objectif : Identifier les personnage de votre appareil

Teams téléphones et affichages s’adaptent à l’un des deux personnage : 

- Appareils personnels
- Appareils d’espace partagé

Les appareils personnels et partagés ont des rôles et des utilisations différents. 

**Appareils personnels :** 

- Généralement attribué à un utilisateur, avec le compte de cet utilisateur et activé avec Teams fonctionnalité pour accéder au service.
- Les appareils personnels ont une relation un-à-un, avec un appareil par utilisateur.
- Peut être jumelé avec le client de bureau Teams et utiliser des fonctionnalités telles que Better Together
- Peut se connecter à un casque, câblé ou sans fil
- Les fonctionnalités supplémentaires sur les appareils personnels incluent la fonctionnalité d’hot-desking et l’écran d’accueil. 

**Appareils d’espace partagé :**

- Effectuez une fonction spécifique, telle qu’un téléphone local commun ou un appareil de salle de réunion, et vous avez besoin d’un compte dédié et d’une licence de fonctionnalité pour accéder au service.
- Les appareils partagés ont une relation un-à-plusieurs : un seul appareil partagé par de nombreux utilisateurs.
- Déployés dans des espaces partagés tels que des salles de réunion, des zones de réception ou des étages de fabrication. 
- Leurs interfaces utilisateur (IU) sont spécifiques à leur fonction, telles que la zone commune Téléphone l’interface utilisateur ou l’interface utilisateur des salles de réunion dépendent de la fonction et de la position du périphérique partagé.
- Exigez une configuration et une définition facultative pour vous assurer que les paramètres ne sont pas modifiés, ou pour empêcher le compte de se dé dé signer. 
- Des fonctionnalités supplémentaires sur les appareils d’espace partagé incluent la recherche sur les téléphones de zone communs et la fonctionnalité d’utilisation de la fonctionnalité d’auto-désenchement avec un délai d’inactivité

### <a name="objective-how-many-personal-and-shared-space-devices-do-you-need"></a>Objectif : Combien d’appareils d’espaces personnels et partagés avez-vous besoin ?

À présent que vous avez identifié les personnage de votre appareil, vous devez déterminer les périphériques certifiés que vous voulez utiliser et le nombre d’appareils dont vous avez besoin. Pour vous aider à prendre cette décision, prenons en compte les questions suivantes : 

- Combien d’appareils personnels sont requis et qui en aura un ?
- Combien de salles ou d’espaces nécessitent des appareils partagés ? Chaque espace aura-t-il le même type d’appareil ? 
- Vos appareils devront-ils répondre à des exigences spécifiques ?
    - Il peut s’agir, par exemple, de la taille d’écran, du facteur de formulaire, du fabricant ou du modèle. Pour obtenir la liste des téléphones et affichages certifiés, voir [Microsoft Teams périphériques certifiés.](teams-ip-phones.md)
-  Avez-vous besoin Teams téléphones portables ou Teams’écran ? Pour obtenir la liste des fonctionnalités pris en charge par Teams, consultez Téléphones pour [Microsoft Teams](phones-for-teams.md#features-supported-by-teams-phones) et pour [](teams-displays.md#features-supported-by-teams-displays)obtenir la liste des fonctionnalités pris en charge par les écrans Teams, consultez les Microsoft Teams.
- Avez-vous suffisamment d’appareils pour les nouveaux utilisateurs ou un processus pour les nouvelles commandes et la livraison ?
- Vos appareils seront-ils disponibles pour maintenance ou en cas de problèmes matériels ? La possibilité d’échanger rapidement un appareil empêche toute interruption de l’expérience utilisateur.

## <a name="task-2-what-are-your-licensing-requirements"></a>Tâche 2 : quelles sont vos exigences en matière de licence ? 

Vous savez maintenant combien d’appareils vous avez besoin, l’étape suivante consiste à déterminer le nombre de licences nécessaires. Teams téléphones et les écrans nécessitent des licences d’accès à Microsoft Teams et Microsoft 365.

Les appareils partagés et personnels auront besoin de licences différentes. Pour les appareils personnels, les licences attribuées à des comptes d’utilisateurs peuvent être utilisées. Les appareils partagés ont besoin de licences spécifiques à leur fonction. Pour les téléphones et les affichages, les licences applicables sont la licence zone [Téléphone](../set-up-common-area-phones.md#step-1---buy-the-licenses) pour la Microsoft Teams et la licence Salles Microsoft Teams Standard [licence.](../rooms/rooms-licensing.md#licensing-solutions-for-shared-communication-devices)

Pour plus d’informations et pour comparer vos options de licence, voir [Microsoft 365 de licences proposées.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) 

## <a name="task-3-what-are-your-dependencies"></a>Tâche 3 : Quelles sont vos dépendances ? 

### <a name="objective-plan-your-device-identities"></a>Objectif : Planifier les identités de votre appareil

Les identités permettent aux appareils d’accéder Microsoft 365 services de sécurité et doivent faciliter la découverte, la gestion et la connexion des appareils au sein de votre organisation. Pour ce faire, prenez en compte les considérations suivantes lors de la planification des identités d’appareils :

- Noms des principaux utilisateurs, format et domaine
- Noms d’affichage
- Découverte du carnet d’adresses
- Types d’appareils personnels et d’espace partagé
- Licence attribuée à un groupe ou à l’utilisateur

### <a name="objective-review-conditional-access-policies"></a>Objectif : Passer en revue les stratégies d’accès conditionnel

Azure Active Directory d’accès conditionnel sont des conditions supplémentaires qui doivent être respectées pour qu’un appareil puisse être connecté.

Lorsque vous planifiez votre déploiement

- Examinez les stratégies d’accès conditionnel existantes qui peuvent Teams vos téléphones et affichages. Vous pouvez le faire dans le Centre Azure AD’administration à l’aide de l’outil [Si](/azure/active-directory/conditional-access/what-if-tool) et des [journaux de connexion](/azure/active-directory/reports-monitoring/concept-sign-ins)

- Planifier les nouvelles règles si nécessaire

- Utilisez les fonctionnalités d’accès conditionnel telles que les filtres de l’appareil pour appliquer des Teams aux téléphones et aux affichages.

>[!NOTE]
>Certaines stratégies d’accès conditionnel ne sont pas prise en charge par les appareils Android. Pour obtenir des conseils et consulter des recommandations, voir Les meilleures pratiques d’authentification pour Teams [appareils Android.](authentication-best-practices-for-android-devices.md)

## <a name="task-4-prepare-your-environment"></a>Tâche 4 : préparer votre environnement

### <a name="objective-plan-network-basics"></a>Objectif : Planifier les bases du réseau

Teams Téléphone et les écrans nécessitent un accès à Internet pour se connecter Teams et fonctionner comme prévu. Pour préparer votre réseau au déploiement, prenons en compte les considérations suivantes :

- Votre infrastructure réseau a-t-elle suffisamment de capacité ? Envisagez de changer de ports, de points d’accès sans fil et d’autres éléments de couverture.
- Si vous utilisez des VLAN et DHCP, vos étendues sont-elles limitées en conséquence ?
- Évaluez et testez les chemins réseau de l’endroit où les appareils sont déployés vers Microsoft 365. 
- Ouvrez les ports et les URL de pare-feu requis Microsoft 365 les instructions.
- Examinez et testez les exigences et la configuration E911 pour la précision de l’emplacement et la conformité. 
- Évitez d’utiliser un serveur proxy et optimisez les chemins d’accès multimédia pour la fiabilité et la qualité.

### <a name="objective-physical-considerations"></a>Objectif : Considérations physiques

Prenez en compte les espaces physiques dans Teams et vos écrans seront utilisés.

Les aspects clés sont les suivants :

- **Alimentation :** Avez-vous suffisamment de prises électriques ? Si l’appareil a besoin d’une source d’alimentation externe, quelle est la fermeture possible de l’appareil sur une prise ?
- **Emplacement de l’appareil :** Où se trouve votre appareil physiquement ? Support de révision, supports muraux et autres accessoires du fabricant d’origine (OEM).
- **Sécurité :** Votre appareil doit-il être verrouillé dans certains espaces ?
- **Accessibilité :** L’appareil répond-il aux exigences d’accessibilité de son utilisateur principal ? Pensez à l’endroit où il est placé, à la longueur du câble, au combiné ou à l’utilisation du casque.

### <a name="task-5-how-will-you-manage-deployed-devices"></a>Tâche 5 : Comment allez-vous gérer les appareils déployés ?

Teams téléphones et affichages sont gérés de deux à trois portails Microsoft 365 et leurs modules PowerShell respectifs : 

#### <a name="azure-active-directory-admin-center"></a>Azure Active Directory d’administration

Utiliser le Azure AD d’administration pour gérer

- Toutes les tâches liées à l’identité Teams téléphones et les affichages
- Stratégies d’accès conditionnel 
- Réinitialisations de mot de passe

#### <a name="teams-admin-center"></a>Teams d’administration

Utiliser le Teams d’administration pour gérer

- [Paramètres de l’appareil pour Teams](../business-voice/manage-devices.md)
- [Profils de configuration](device-management.md#use-configuration-profiles-in-teams)
- [Marquage de l’appareil](manage-device-tags.md)
- [Sign-in and sign-out remote](remote-sign-in-and-sign-out.md)
- Analyse des appels  
- Microprogramme
- Résolution des problèmes et téléchargement des journaux

#### <a name="endpoint-manager-admin-center-if-you-use-intune-for-device-management"></a>Endpoint Manager d’administration (si vous utilisez Intune pour la gestion des appareils)

Utilisez le Endpoint Manager d’administration pour gérer : 

- Stratégies de conformité des appareils
- Restrictions d’inscription
- Identificateurs d’appareil d’entreprise
- Filtres de l’appareil
