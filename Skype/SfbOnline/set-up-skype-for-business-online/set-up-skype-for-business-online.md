---
title: Configurer Skype Entreprise Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 40296968-e779-4259-980b-c2de1c044c6e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365E_SkypeforBusinessON
- O365M_SkypeforBusinessON
- O365P_SkypeforBusinessON
ms.custom:
- Setup
- Alchemy
- LIL_Placement
description: 'Familiarisez-vous avec la configuration de votre domaine, des utilisateurs, de la messagerie instantanée et de la présence de votre organisation pour l’installation de Skype entreprise. Apprenez-en plus sur la configuration de l’audioconférence, du système téléphonique et des plans d’appel et de la diffusion de réunion Skype. '
ms.openlocfilehash: 239e1c39563594ffe1ff106284bbbf912367fb88
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2019
ms.locfileid: "35792619"
---
# <a name="set-up-skype-for-business-online"></a>Configurer Skype Entreprise Online

Vous devez posséder des droits d'administrateur global d'Office 365 pour configurer Skype Entreprise. Si vous avez un pare-feu ou un serveur proxy qui restreint l'accès à certaines parties du web, envisagez de recourir aux compétences d'un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) qui configurera Skype Entreprise pour vous.

## <a name="setting-up-skype"></a>Configuration de Skype

Il semble que vous ayez besoin d'aide pour configurer Skype avec votre abonnement Office 365. Vous pouvez suivre la procédure décrite dans cet article pour terminer votre configuration.

## <a name="1-plan-for-skype-for-business"></a>1. Offre pour Skype Entreprise

Si vous disposez d' **[Office 365 Business Premium](https://products.office.com/en-us/business/office-365-business-premium)** ou de **Business Essentials**, vous pouvez utiliser Skype Entreprise pour passer des appels en ligne à d'autres personnes de votre entreprise incluses dans votre abonnement. Par exemple, si votre entreprise dispose de 10 personnes, vous pourrez [commencer à utiliser Skype entreprise pour la messagerie instantanée et les réunions en ligne et réunions en ligne](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) [avec Skype entreprise](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) avec Skype entreprise, après avoir effectué les étapes suivantes 2-6. Vous pouvez aussi organiser [une réunion Skype entreprise dans Outlook](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) en réunion en ligne.

Si vous voulez utiliser Skype Entreprise pour passer et recevoir des **appels** avec des personnes *externes*  à votre entreprise :

- **Option 1. Utilisez l'application gratuite [Skype](https://www.skype.com/)**. Si votre entreprise est très petite (par exemple, une ou deux personnes), l'application Skype est la meilleure solution. Elle est plus économique pour les appels nationaux et internationaux. Vous pouvez toujours organiser des conférences téléphoniques, passer des appels vidéo et partager votre bureau pour des présentations. [Découvrez les tarifs et les options de paiement](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled).

- **Option 2. Passez au niveau supérieur et achetez le système téléphonique et un forfait d'appels Office 365**. Le moyen le plus simple de savoir combien de coûts, puis de définir le commutateur, est de [contacter le support technique pour les produits pour les entreprises-aide](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) de l’administrateur et de leur faire tout le temps.

Pour en savoir plus, voir [planifier votre installation d’Office 365 pour les entreprises](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype).

## <a name="2-sign-in-to-office-365"></a>2. Connexion à Office 365
<a name="bkmk_signin"> </a>

Skype Entreprise Online fait partie de la suite de services Office 365. Pour configurer Skype Entreprise Online, vous devez vous connecter à Office 365. Voici comment procéder :

1. Recherchez votre ID d'utilisateur Office 365 (par exemple,  <em>rob@fourthcoffee.com</em>  ). Vous avez reçu un courrier électronique de l'équipe Microsoft Online Services qui contient l'identifiant utilisateur Office 365 que vous avez créé lorsque vous avez acheté Skype Entreprise Online. Le courrier ressemble à ceci :

    ![Exemple de courrier électronique de bienvenue que vous recevez après vous être inscrit à Skype Entreprise Online. Il contient votre identifiant utilisateur Office 365.](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)

2. Connectez-vous au centre d’administration, puis entrez votre ID utilisateur et votre mot de passe Office 365. Après vous être connecté, vous verrez le centre d’administration Microsoft 365:

    ![Exemple illustrant le centre d’administration lorsque vous disposez d’une offre Skype entreprise online.](../images/ed1d9906-e717-450b-81a3-ce6679bd1be1.png)

## <a name="3-set-up-your-domain-and-users"></a>3. Configuration de votre domaine et de vos utilisateurs
<a name="bkmk_users"> </a>

Maintenant que vous êtes connecté à Office 365, vous pouvez configurer votre domaine et les personnes de votre organisation qui peuvent utiliser Skype Entreprise Online.

1. [Ajouter un domaine et des utilisateurs à Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): utilisez l’Assistant Installation d’Office 365 pour configurer votre domaine personnalisé (par exemple, *fourthcoffee.com*) avec Office 365. **Par défaut, l'assistant d'installation d'Office 365 inclut la configuration de Skype Entreprise Online et la création de vos ID utilisateur Skype Entreprise.** Si vous avez déjà utilisé l'assistant pour configurer votre domaine pour Office 365, vous avez déjà effectué cette étape.

2. [Vérifier votre domaine et vos connexions DNS](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0) : utilisez notre outil de résolution des problèmes liés aux domaines pour vérifier que votre domaine et vos paramètres DNS sont corrects. Cette opération vous permettra d'éviter tout problème lié aux paramètres DNS et d'identifier ainsi les problèmes de configuration rencontrés en toute simplicité.

3. [URL et plages d’adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): la plupart des petites entreprises ne nécessitent pas cette étape. **Toutefois, si vous avez un pare-feu ou un serveur proxy qui limite l’accès aux différentes parties du Web**, vous devez créer des règles pour autoriser l’accès aux points de terminaison Skype entreprise online. Il s’agit d’une avancée avancée qui est effectuée par un utilisateur expérimenté dans la configuration de pare-feu et de serveurs proxy. Si vous ne l’avez pas encore fait, envisagez d’utiliser un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) pour configurer Skype entreprise pour vous.

## <a name="4-set-up-im-and-presence-in-your-organization"></a>4. Configuration de la messagerie instantanée et de la présence dans votre organisation
<a name="bkmk_IM"> </a>

La messagerie instantanée (MI) et la présence ([Contrôle de l'accès à vos informations de présence dans Skype Entreprise](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)) sont des fonctionnalités de base intégrées à Skype Entreprise. Par défaut, les personnes de votre entreprise peuvent utiliser Skype et la messagerie instantanée pour communiquer entre elles.

1. **Choisissez avec qui vos utilisateurs de Skype Entreprise peuvent également communiquer :**

   - [Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise](allow-users-to-contact-external-skype-for-business-users.md) Vous *et*  les utilisateurs de l'autre entreprise devrez configurer vos systèmes.

     **IMPORTANT**: Si votre organisation dispose de deux domaines, par exemple rob@contosowest.com et ina@contosoeast.com, cette étape est requise pour permettre à tous les utilisateurs de communiquer entre eux.

   - [Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md) en dehors de votre entreprise

2. **Sélectionnez les utilisateurs qui voient si vos collègues sont en ligne :** la fonctionnalité de présence indique qui est en ligne et sa disponibilité, à savoir Disponible, Occupé(e), Absent(e) ou En présentation.

    ![An example of a person's online status with a personal message.](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)

    Vous pouvez choisir les paramètres par défaut de toutes les personnes de votre entreprise :

   - Afficher automatiquement la présence en ligne d'une personne pour tout le monde au sein de l'organisation

   - Afficher la présence en ligne d'une personne uniquement à ses contacts

Pour obtenir des instructions, consultez [Configuration de la présence dans Skype Entreprise Online](configure-presence-in-skype-for-business-online.md).

## <a name="5-download-and-install-skype-for-business"></a>5. Télécharger et installer Skype Entreprise
<a name="bkmk_download"> </a>

Pour utiliser Skype Entreprise sur votre ordinateur PC ou Mac ou votre appareil mobile, vous et d'autres personnes de votre entreprise devez d'abord installer le programme Skype Entreprise téléchargé sur vos appareils.

- [Installer Skype Entreprise](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb) : instructions relatives au téléchargement de l'application à partir du portail Office 365 et à son installation sur votre PC ou Mac.

- [Déploiement du client Skype entreprise dans Office 365](deploy-the-skype-for-business-client-in-office-365.md): instructions de déploiement de l’application dans une grande entreprise.

- [Installer Skype Entreprise](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb) : téléchargez, installez et connectez-vous à Skype Entreprise sur des appareils Android, iOS et des téléphones Windows.

- [Activation ou désactivation des notifications par téléphone mobile](turn-on-or-off-mobile-phone-notifications.md): lorsque vous avez installé Skype entreprise sur un appareil mobile, vous et d’autres personnes de votre entreprise pouvez recevoir des alertes concernant les messages instantanés entrants et manqués.

## <a name="6-test-to-make-sure-everything-is-working"></a>6. Test pour s'assurer que tout fonctionne
<a name="bkmk_test"> </a>

Commencez par déterminer si vous et d'autres personnes de votre entreprise pouvez [Vidéo : connexion à Skype Entreprise et déconnexion](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451). Vérifiez que vous pouvez communiquer par messages instantanés, voir la présence les uns des autres, puis essayez de lancer une réunion rapide.

Des problèmes ? Procédez comme suit :

- [Vous avez besoin d'aide pour vous connecter à Skype Entreprise ?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) des problèmes de connexion usuels.

- [Contacter le support Office 365 pour les entreprises - Aide de l'administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). Nous sommes là pour vous aider !

## <a name="do-you-want-to-set-up-other-available-features"></a>Souhaitez-vous configurer d'autres fonctionnalités disponibles ?
<a name="bkmk_more"> </a>

Avant de configurer davantage de fonctionnalités, assurez-vous que vous avez des licences pour eux. [Licences de compléments pour Skype Entreprise et Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="set-up-audio-conferencing"></a>Configurer l'audioconférence

Parfois, des personnes de votre organisation devront utiliser un téléphone pour rejoindre une réunion. Skype Entreprise inclut la fonction d'audioconférence pour cette situation ! Il est possible de rejoindre des réunions Skype Entreprise en utilisant un téléphone au lieu de l'application Skype Entreprise sur un appareil mobile ou un PC.

### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a>Configurer le système téléphonique Office 365 et l'offre d'appels Office 365

La fonction de système téléphonique dans Office 365 fournit un système téléphonique pour votre entreprise. Les appels passés vers d'autres utilisateurs de Skype Entreprise dans votre organisation sont gratuits, et vos employés peuvent recevoir des messages vocaux provenant d'autres employés ou de l'extérieur de l'entreprise. Voici les avantages du système téléphonique.

Lorsque vous ajoutez le service Forfait d'appels, vos employés obtiennent un numéro de téléphone principal dans Skype Entreprise. Ils peuvent émettre et recevoir des appels provenant de numéros extérieurs à votre entreprise. Ils peuvent passer des appels via un téléphone VoIP, un PC ou un appareil mobile. Et, en cas d'urgence, ils peuvent appeler le 911 pour obtenir de l'aide.

Pour configurer cette fonction, consultez la rubrique Configurer les offres d'appels.

### <a name="set-up-skype-meeting-broadcast"></a>Configurer Diffusion de réunion Skype

Diffusion de réunion Skype est une fonctionnalité qui vous permet de créer, héberger et diffuser des réunions avec un maximum de 10 000 participants. **Pour en savoir plus sur son fonctionnement, consultez la rubrique [Qu'est-ce qu'une diffusion de réunion Skype ?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**

Voici un aperçu des étapes requises pour configurer Diffusion de réunion Skype:

1. [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) : affectez des licences **Skype Entreprise Online** ou **Enterprise Plan** à toutes les personnes qui vont **organiser** une diffusion de réunion.

2. [Activer la diffusion de réunion Skype](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md): cette fonctionnalité n’est pas activée par défaut. Une fois la fonctionnalité activée, vos utilisateurs pourront organiser des diffusions de réunion avec d'autres membres de votre organisation.

3. [Configurer votre réseau pour la diffusion de réunion Skype](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md): Si vous souhaitez héberger des webinaires et d’autres diffusions avec des participants extérieurs à votre organisation, vous devez configurer votre réseau.

4. [Planifier une diffusion de réunion Skype](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) et disposer d’une [diffusion de réunion Skype](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe): Veillez à ce que la diffusion de réunion fonctionne en *https://portal.broadcast.skype.com* planifiant une diffusion de réunion Skype à partir de et en faisant en sorte que quelqu’un tente de participer à la réunion.

## <a name="learn-about-network-connectivity-requirements"></a>Autres informations relatives à la connectivité réseau
<a name="bkmk_more"> </a>

La qualité de l'image, du son et du partage d'applications dans Skype Entreprise est fortement influencée par la qualité de la connexion de votre réseau étendu. Pour profiter d'une expérience optimale, vous devez disposer d'une connexion de haute qualité entre le réseau de votre entreprise et Skype Entreprise Online. Pour savoir comment optimiser votre réseau, consultez la rubrique [Optimiser les performances de Skype Entreprise Online](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802).

## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a>Vous avez terminé la configuration ? Prise en main de Skype Entreprise
<a name="bkmk_more"> </a>

[Formation Skype entreprise](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): consultez cette liste des rubriques de formation pour vous initier rapidement.

[Lancement d'une téléconférence avec Skype Entreprise](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)

[Définir les options de périphérique vidéo dans Skype Entreprise](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)

[Émission et réception d'un appel vidéo dans Skype Entreprise](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)

[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>Voir aussi
<a name="bkmk_more"> </a>

[Planifier une connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online](https://go.microsoft.com/fwlink/p/?linkid=400791)



