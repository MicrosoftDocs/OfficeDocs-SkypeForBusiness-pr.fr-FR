---
title: Gérer les fonctionnalités de Microsoft Teams dans votre organisation Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: Découvrez comment activer ou désactiver les applications Microsoft Teams dans votre organisation Office 365, notamment des onglets, des connecteurs, des robots ou n’importe quelle combinaison des trois.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7411494c3baa56c1761ee3bcd69c2d49fdd4a961
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26533166"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a>Gérer les fonctionnalités de Microsoft Teams dans votre organisation Office 365

Tous les paramètres d’équipes seront bientôt migrés au nouveau Microsoft Teams & Skype entreprise centre d’administration. La seule fonctionnalité équipes qui est gérée dans le centre d’administration Office 365 est Apps. 

Sauf indication contraire, la valeur par défaut d’une option est **sur**.

## <a name="office-365-tenant-wide-settings"></a>Paramètres à l'échelle du client Office 365 

Dans les **paramètres au niveau du client**, vous pouvez activer ou désactiver les applications.

Pour modifier les **paramètres au niveau du client** pour les équipes, accédez au portail Microsoft Teams & Skype entreprise centre d’administration et sélectionnez **portail hérité**. Sélectionnez **Paramètres** > **Services et compléments** > **Microsoft Teams**. Si vous êtes connecté en tant qu’administrateur d’Office 365, ce lien vous dirige sur cette option : 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a>Applications

Les applications sont des onglets, des connecteurs, des bots ou n'importe quelle combinaison de ces éléments, fournis par un service tiers. Des stratégies d'administration de Teams peuvent être configurées dans le Centre d'administration Office 365 pour contrôler l'autorisation d'applications tierces externes. Ces stratégies permettent de spécifier les applications qui sont autorisées et non autorisées, le nouveau comportement de l’application externe, et si les applications côté-chargement est autorisé. 

La section **Applications** vous permet de configurer les paramètres suivants pour votre organisation : 

![Capture d'écran de la section Applications.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- **Autoriser les applications externes dans Microsoft Teams :** lorsque cette option est activée, les utilisateurs peuvent ajouter des onglets et des bots disponibles pour le client Office 365. 
 
    ![Capture d'écran de la commande Autoriser les applications externes dans la section Applications.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- **Activer les applications externes nouvelles par défaut** : lorsque cette option est activée, les utilisateurs peuvent activer les nouvelles applications dès qu'elles sont ajoutées au catalogue d'applications Teams. Désactivez cette option si vous souhaitez contrôler les nouvelles applications. Bien sûr, si vous la désactivez, n'oubliez pas de vérifier régulièrement les nouvelles applications afin que votre organisation ne passe pas à côté de nouvelles applications intéressantes. 

- **Chargement de version test autoriser des applications externes**: lorsque ce commutateur est activé, les utilisateurs peuvent installer et activer des robots personnalisés et des onglets. 

Pour en savoir plus, consultez la rubrique [Paramètres d'administration pour les applications dans Microsoft Teams](admin-settings.md). 

## <a name="teams-org-wide-settings"></a>Paramètres d’échelle de l’organisation équipes

Vous pouvez contrôler les paramètres utilisateur à l’échelle de l’organisation dans le Microsoft Teams & Skype entreprise centre d’administration. Pour modifier les paramètres d’échelle de l’organisation, accédez à la Skype Microsoft Business centre d’administration, puis sélectionnez **paramètres de l’organisation**. Vous pouvez configurer les paramètres suivants.

### <a name="external-access"></a>Accès externe

**Accès externe** permet à vos équipes et les Skype pour les utilisateurs professionnels de communiquer avec des utilisateurs qui sont en dehors de votre organisation. Pour configurer l’accès externe, accédez à [laisser votre conversation d’utilisateurs équipes et communiquer avec les utilisateurs d’une autre organisation équipes](let-your-teams-users-communicate-with-other-people.md).

### <a name="guest-access"></a>Accès invité

**Accès invité** dans Microsoft Teams permet aux équipes de votre organisation de collaborer avec des personnes extérieures à votre organisation par leur accorder l’accès aux équipes et canaux. Toute personne possédant un compte de messagerie consommateur ou de l’entreprise, comme Outlook, Gmail ou d’autres personnes, peut participer à en tant qu’invité dans les équipes avec accès total aux conversations de l’équipe, des réunions et des fichiers. Pour plus d’informations, consultez [accès invité dans les équipes Microsoft](guest-access.md).

### <a name="teams-settings"></a>Paramètres d’équipes

Dans **paramètres d’équipes**, vous pouvez définir l’intégration de messagerie, les options de stockage dans le nuage, Skype pour l’interopérabilité d’entreprise et des périphériques.

#### <a name="email-integration"></a>Intégration de la messagerie

Activez cette fonctionnalité pour que les utilisateurs puissent envoyer des e-mails à un canal dans Teams, en utilisant l’adresse de messagerie du canal. Les utilisateurs peuvent envoyer des e-mails pour tous les canaux appartenant à une équipe dont ils sont propriétaires. Les utilisateurs peuvent également envoyer des messages électroniques à n’importe quel canal dans une équipe Ajout de connecteurs activée pour les membres de l’équipe. Pour activer l’intégration de messagerie, assurez-vous que **Autoriser les utilisateurs à envoyer des messages électroniques à une adresse de messagerie de canal** est **activé**. 

#### <a name="files"></a>Fichiers

Ici vous pouvez activer ou désactiver les options de stockage fichier cloud et de partage des fichiers. 

Les utilisateurs peuvent charger et partager des fichiers à partir de services de stockage cloud dans les canaux et conversations Teams. Options de stockage en nuage dans les équipes incluent actuellement ShareFile, échange, zone et Google lecteur. Activez l'option pour les fournisseurs de stockage cloud que votre organisation souhaite utiliser.

#### <a name="organization"></a>Organisation

Ici, vous pouvez activer sous l’onglet **organisation** , qui affiche l’organigramme détaillé pour l’organisation de l’utilisateur. Pour plus d’informations, voir [utilisation de l’onglet organisation dans les équipes](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).

#### <a name="skype-for-business-interop"></a>Skype pour l’interopérabilité d’entreprise

Utilisez ce paramètre pour permettre aux équipes aux utilisateurs de converser avec Skype pour les utilisateurs professionnels. Pour plus d’informations sur l’interopérabilité entre les équipes et Skype pour les entreprises, accédez à [comprendre les équipes Microsoft et Skype pour l’interopérabilité et coexistence d’entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

#### <a name="devices"></a>Périphériques

Ces paramètres contrôlent le comportement de compte de ressource pour les périphériques de Surface Hub participation à des réunions Teams Microsoft. Ces paramètres permettent de configurer les exigences d’authentification, nécessitent un code confidentiel de contenu et activer des comptes de ressource Hub de la surface d’exposition pour envoyer des messages.

- **Exiger une forme secondaire d’authentification pour accéder au contenu de réunion** – sélectionnez le niveau d’accès des utilisateurs lorsqu’ils entrent le contenu ÉPINGLER.
- **Définir le code confidentiel de contenu** – les utilisateurs doivent entrer ce code confidentiel pour empêcher l’accès non autorisé à des documents. Cela empêche un utilisateur non autorisé à partir de participer à des réunions à venir et la navigation des pièces jointes.
- **Comptes de ressources peuvent envoyer des messages** – activer ce paramètre **sur** des messages à envoyer à partir du compte de ressource Hub de la surface d’exposition.

#### <a name="search"></a>Recherche

Recherche dans l’annuaire sur lesquelles porte Teams Microsoft utilise la stratégie de carnet d’adresses Exchange (APB) pour permettre aux organisations de créer des limites virtuels qui contrôlent comment les utilisateurs peuvent rechercher et communiquer avec d’autres utilisateurs dans leur organisation. Vous pouvez souhaiter utiliser une recherche dans l’annuaire étendue dans les situations suivantes :

- Votre organisation possède plusieurs sociétés dans son client que vous souhaitez conserver séparément. 
- Votre école veut limiter les conversations entre la faculté et aux étudiants. 

Changer ce paramètre **sur** pour activer les recherches dans l’annuaire étendue définie.

### <a name="teams-upgrade"></a>Mise à niveau des équipes

Vous pouvez utiliser ces paramètres pour configurer la façon dont vos utilisateurs passeront de Skype pour les entreprises à Microsoft Teams. 

#### <a name="coexistence-mode"></a>Mode de coexistence
Vous pouvez spécifier un mode de coexistence : **équipes uniquement**, **îles** (équipes et Skype pour sera Business coexister) ou **Skype pour les entreprises uniquement**. Le mode de Coexistence que vous choisissez détermine le routage des appels entrants et salles de conversation et l’application qui est utilisée par l’utilisateur pour démarrer des conversations et les appels ou pour planifier des réunions. Pour plus d’informations sur les modes de coexistence, accédez à [comprendre les équipes Microsoft et Skype pour l’interopérabilité et coexistence d’entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

#### <a name="app-preferences"></a>Préférences de l’application

Vous pouvez sélectionner l’application que les utilisateurs utiliseront pour joindre Skype pour les entreprises réunions (Skype pour l' [Application de réunions Skype](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)ou de l’entreprise). Ce paramètre n’est pas dépendant du paramètre de mode de coexistence.

## <a name="how-can-i-tell-which-features-are-available"></a>Comment puis-je savoir quelles fonctionnalités sont disponibles ?

Voir la [Feuille de route Office 365](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) pour plus d’informations sur les nouvelles fonctionnalités d’équipes. Pour plus d’informations sur les fonctionnalités nouvelles et à venir, consultez la page équipes [What ' s New](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) et les [équipes Microsoft de la Communauté Tech blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531) pour les équipes. 
