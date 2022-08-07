---
title: Planifier votre déploiement pour les appareils téléphoniques et les écrans Teams
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
description: Cet article fournit et présente les tâches et les étapes de déploiement de téléphones et d’affichages Teams dans votre organisation.
ms.collection:
- M365-voice
- Teams_ITAdmin_Devices
ms.openlocfilehash: 5172d230823088141c58e3d2b58e1c3b579268b3
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272389"
---
# <a name="plan-your-deployment-for-teams-phone-devices-and-displays"></a>Planifier votre déploiement pour les appareils téléphoniques et les écrans Teams

Un déploiement réussi des appareils téléphoniques Teams et des affichages Teams commence par la planification. Cet article vous guide tout au long des tâches et des étapes de déploiement de ces appareils dans votre organisation. Il fournit également des conseils sur l’utilisation des appareils, les licences, l’intégration à votre environnement, les points de contact et la gestion.

> [!TIP]
> [Microsoft 365 Adoption Hub](https://adoption.microsoft.com/) est un excellent endroit pour commencer votre parcours d’adoption avec Microsoft Teams.

## <a name="task-1-what-are-your-deployment-objectives"></a>Tâche 1 : Quels sont vos objectifs de déploiement ?

La planification du déploiement des téléphones et affichages Teams dans votre organisation commence par vos objectifs de déploiement. Les appareils Teams prennent en charge le travail hybride dans les salles de réunion, les bureaux et d’autres espaces fonctionnels. Vous devez déterminer où ces appareils seront utilisés et par qui.

### <a name="objective-identify-your-device-personas"></a>Objectif : Identifier les personnages de votre appareil

Les téléphones et les écrans Teams s’adaptent à l’un des deux personnages suivants : 

- Appareils personnels
- Appareils d’espace partagé

Les appareils personnels et partagés ont des rôles et des utilisations différents. 

**Appareils personnels :** 

- Généralement affecté à un utilisateur, connecté avec le compte de cet utilisateur et activé avec une licence de fonctionnalité Teams pour accéder au service.
- Considérez les appareils personnels comme ayant une relation un-à-un, avec un appareil par utilisateur.
- Peut être associé au client de bureau Teams et utiliser des fonctionnalités telles que Better Together
- Peut se connecter à un casque, câblé ou sans fil
- D’autres fonctionnalités sur les appareils personnels incluent la mise à l’eau à chaud et l’écran d’accueil. 

**Appareils d’espace partagé :**

- Effectuez une fonction spécifique, comme un téléphone de zone commune ou un appareil de salle de réunion, et nécessitez un compte dédié et une licence de fonctionnalité pour accéder au service.
- Considérez les appareils partagés comme ayant une relation un-à-plusieurs : un appareil partagé par de nombreux utilisateurs.
- Déployé dans des espaces partagés tels que des salles de réunion, des zones de réception ou des planchers de fabrication. 
- Leurs interfaces utilisateur sont spécifiques à leur fonction, telle que l’interface utilisateur de Common Area Phone, ou l’interface utilisateur de la salle de réunion dépend de la fonction et du positionnement de l’appareil partagé.
- Exiger une configuration et un renforcement facultatif pour garantir que les paramètres ne sont pas modifiés ou pour empêcher le compte de se déconnecter. 
- D’autres fonctionnalités sur les appareils d’espace partagé incluent la recherche sur les téléphones de zone commune et la mise à l’eau à chaud avec délai d’inactivité

### <a name="objective-how-many-personal-and-shared-space-devices-do-you-need"></a>Objectif : De combien d’appareils d’espace personnel et partagé avez-vous besoin ?

Maintenant que vous avez identifié vos personnages d’appareil, vous devez déterminer les appareils certifiés que vous souhaitez utiliser et le nombre d’appareils dont vous avez besoin. Pour vous aider à prendre cette décision, tenez compte des questions suivantes : 

- Combien d’appareils personnels sont nécessaires et qui en aura un ?
- Combien de salles ou d’espaces nécessitent des appareils partagés ? Chaque espace aura-t-il le même type d’appareil ? 
- Vos appareils devront-ils répondre à des exigences spécifiques ?
    - Par exemple, la taille de l’écran, le facteur de forme et le fabricant ou le modèle ? Pour obtenir la liste des téléphones certifiés et des écrans, consultez [les appareils certifiés Microsoft Teams](teams-ip-phones.md).
-  Avez-vous besoin de téléphones Teams ou d’affichages Teams ? Pour obtenir la liste des fonctionnalités prises en charge par les téléphones Teams, consultez [Téléphones pour Microsoft Teams](phones-for-teams.md#features-supported-by-teams-phones) et pour obtenir la liste des fonctionnalités prises en charge par teams, consultez les [affichages Microsoft Teams](teams-displays.md#features-supported-by-teams-displays).
- Disposez-vous d’un nombre suffisant d’appareils pour les nouveaux utilisateurs ou d’un processus pour les nouvelles commandes et remises ?
- Disposerez-vous d’appareils de rechange disponibles pour la maintenance ou en cas de problèmes matériels ? La possibilité d’échanger rapidement un appareil empêche les interruptions de l’expérience utilisateur.

## <a name="task-2-what-are-your-licensing-requirements"></a>Tâche 2 : Quelles sont vos exigences en matière de licences ? 

Maintenant que vous savez combien d’appareils vous avez besoin, l’étape suivante consiste à déterminer le nombre de licences nécessaires. Les téléphones et les écrans Teams nécessitent des licences pour accéder à Microsoft Teams et Microsoft 365.

Les appareils partagés et personnels auront besoin de licences différentes. Pour les appareils personnels, les licences attribuées aux comptes d’utilisateur peuvent être utilisées. Les appareils partagés ont besoin de licences spécifiques à leur fonction. Pour les téléphones et les écrans, les licences applicables sont [la licence Common Area Phone pour Microsoft Teams](../set-up-common-area-phones.md#step-1---buy-the-licenses) et [la licence Salles Microsoft Teams Standard](../rooms/rooms-licensing.md#licensing-solutions-for-shared-communication-devices).

Pour plus d’informations et pour comparer vos options de licence, consultez les [plans de licences Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1). 

## <a name="task-3-what-are-your-dependencies"></a>Tâche 3 : Quelles sont vos dépendances ? 

### <a name="objective-plan-your-device-identities"></a>Objectif : Planifier les identités de votre appareil

Les identités permettent aux appareils d’accéder aux services Microsoft 365 et doivent faciliter la découverte, la gestion et la connexion des appareils au sein de votre organisation. Pour ce faire, tenez compte des éléments suivants lors de la planification des identités d’appareil :

- Noms d’utilisateur principal et leur format et leur domaine
- Noms d’affichage
- Détectabilité du carnet d’adresses
- Types d’appareils d’espace personnel et partagé
- Licences attribuées aux groupes et aux utilisateurs

### <a name="objective-review-conditional-access-policies"></a>Objectif : Passer en revue les stratégies d’accès conditionnel

Les stratégies d’accès conditionnel Azure Active Directory sont des exigences supplémentaires qui doivent être remplies avant qu’un appareil puisse être connecté.

Lors de la planification de votre déploiement

- Passez en revue les stratégies d’accès conditionnel existantes qui peuvent affecter vos téléphones et affichages Teams. Vous pouvez le faire dans le Centre de Administration Azure AD à l’aide de [l’outil What If](/azure/active-directory/conditional-access/what-if-tool) et [des journaux de](/azure/active-directory/reports-monitoring/concept-sign-ins) connexion

- Planifier de nouvelles règles si nécessaire

- Utilisez des fonctionnalités d’accès conditionnel comme les filtres d’appareil pour appliquer des règles aux téléphones et aux écrans Teams.

>[!NOTE]
>Il existe certaines stratégies d’accès conditionnel que les appareils Android ne prennent pas en charge. Pour obtenir des conseils et des bonnes pratiques, consultez les appareils Android, consultez les [meilleures pratiques d’authentification pour les appareils Android Teams](authentication-best-practices-for-android-devices.md).

## <a name="task-4-prepare-your-environment"></a>Tâche 4 : Préparer votre environnement

### <a name="objective-plan-network-basics"></a>Objectif : Planifier les notions de base du réseau

Les appareils et les écrans Teams Phone nécessitent l’accès à Internet pour se connecter à Teams et fonctionner comme prévu. Pour préparer votre réseau au déploiement, tenez compte des éléments suivants :

- Votre infrastructure réseau dispose-t-elle d’une capacité suffisante ? Envisagez de changer de port, de points d’accès sans fil et d’autres couvertures.
- Si vous utilisez des réseaux locaux virtuels et DHCP, vos étendues sont-ils dimensionnées en conséquence ?
- Évaluez et testez les chemins d’accès réseau à partir desquels les appareils sont déployés sur Microsoft 365. 
- Ouvrez les ports et URL de pare-feu requis pour Microsoft 365 conformément aux instructions.
- Passez en revue et testez les exigences et la configuration E911 pour la précision et la conformité de l’emplacement. 
- Évitez d’utiliser un serveur proxy et optimisez les chemins d’accès multimédias pour la fiabilité et la qualité.

### <a name="objective-physical-considerations"></a>Objectif : Considérations physiques

Tenez compte des espaces physiques dans lequel vos téléphones et écrans Teams seront utilisés.

Les aspects clés sont les suivants :

- **Pouvoir:** Avez-vous suffisamment de prises électriques ? Si l’appareil a besoin d’une source d’alimentation externe, à quelle proximité pouvez-vous le positionner sur une prise ?
- **Emplacement de l’appareil :** Où sera physiquement votre appareil ? Passez en revue les stands de bureau, les montages muraux et d’autres accessoires du fabricant d’équipement d’origine (OEM).
- **Sécurité:** Votre appareil doit-il être verrouillé dans certains espaces ?
- **Accessibilité:** L’appareil répond-il aux exigences d’accessibilité de son utilisateur principal ? Tenez compte de l’emplacement, de la longueur du câble et de la facilité d’utilisation du combiné ou du casque.

### <a name="task-5-how-will-you-manage-deployed-devices"></a>Tâche 5 : Comment allez-vous gérer les appareils déployés ?

Les téléphones et les écrans Teams sont gérés à partir de deux à trois portails Microsoft 365 et de leurs modules PowerShell respectifs : 

#### <a name="azure-active-directory-admin-center"></a>Centre de Administration Azure Active Directory

Utiliser le Centre de Administration Azure AD pour gérer

- Toutes les tâches liées à l’identité pour les téléphones et les écrans Teams
- Stratégies d’accès conditionnel 
- Réinitialisations de mot de passe

#### <a name="teams-admin-center"></a>Centre de Administration Teams

Utiliser le Centre de Administration Teams pour gérer

- [Paramètres d’appareil pour Teams](../business-voice/manage-devices.md)
- [Profils de configuration](device-management.md#use-configuration-profiles-in-teams)
- [Balisage des appareils](manage-device-tags.md)
- [Connexion à distance et déconnexion](remote-sign-in-and-sign-out.md)
- Analyse des appels  
- Firmware
- Résolution des problèmes et téléchargement des journaux

#### <a name="endpoint-manager-admin-center-if-you-use-intune-for-device-management"></a>Endpoint Manager Administration Center (si vous utilisez Intune pour la gestion des appareils)

Utilisez le centre de Endpoint Manager Administration pour gérer : 

- Stratégies de conformité des appareils
- Restrictions d’inscription
- Identificateurs d’appareil d’entreprise
- Filtres d’appareil
