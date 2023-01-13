---
title: Thèmes de réunion pour les réunions Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.localizationpriority: medium
search.appverid: MET150
description: Utilisation de ressources d’entreprise approuvées, telles que des images et des logos, pour créer des thèmes de réunion personnalisés pour les réunions Teams au sein de votre organisation.
ms.openlocfilehash: 768c589507cac3f100d2760fe6497872a7f8ee00
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800234"
---
# <a name="meeting-themes-for-teams-meetings"></a>Thèmes de réunion pour les réunions Teams

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

La personnalisation dans les réunions Teams permet aux organisations d’étendre leurs identités visuelles à l’ensemble de l’expérience de réunion. Les images et les couleurs d’une organisation aident à favoriser la création d’une culture d’entreprise interne et à accroître la notoriété globale de la marque auprès des invités. Avec l’aide des équipes de gestion de la marque et de communication d’entreprise d’une organisation, les administrateurs de locataires peuvent facilement configurer et créer des thèmes de réunion pour différentes unités commerciales et services au sein d’un seul locataire.
Par défaut, les utilisateurs sous licence Teams Premium auxquels une stratégie de personnalisation de réunion a été affectée peuvent créer des réunions prenant en charge les thèmes de réunion. Ces réunions présentent des thèmes par défaut, et toute personne qui rejoint les réunions peut voir les thèmes (y compris les utilisateurs internes sans licence, les invités et les utilisateurs anonymes).

> [!NOTE]
> Les participants qui rejoignent Teams via l’expérience web ne pourront pas voir les thèmes de réunion.

## <a name="prerequisites"></a>Conditions préalables

Avant de configurer des thèmes de réunion dans réunions Teams, vérifiez que vous disposez des éléments suivants :

- Accès à Teams Premium référence SKU
- Vous êtes un administrateur disposant d’un accès au Centre d’administration Teams ou vous avez reçu une stratégie de personnalisation
- Votre [logo](#adding-a-custom-logo-image), [image](#adding-a-custom-image) et [couleur](#adding-a-custom-color) personnalisés répondent aux spécifications requises

## <a name="setting-up-meeting-branding"></a>Configuration de la personnalisation de la réunion

Les administrateurs de locataire peuvent configurer et gérer les thèmes de réunion pour les réunions Teams dans le centre d’administration Teams.

### <a name="creating-a-customization-policy"></a>Création d’une stratégie de personnalisation

Pour créer des thèmes de réunion, les administrateurs doivent d’abord créer une stratégie de personnalisation de réunion ou modifier leur stratégie existante.
Pour activer la stratégie d’arrière-plan personnalisée, les administrateurs effectuent les étapes suivantes :

1. Ouvrir le Centre d’administration Teams
2. Sélectionnez **Réunions** dans le volet de navigation
3. Sous **Réunions**, sélectionnez **Stratégies de personnalisation**
4. Sélectionnez une stratégie existante ou créez-en une
5. Dans la stratégie choisie, accédez à la section **Visuels de réunion personnalisés**
6. Activez le paramètre **Actuellement actif** **pour activer** le paramètre
7. Sélectionnez **Enregistrer** pour activer les thèmes de réunion

> [!NOTE]
> Bien que vous puissiez accéder aux visuels de réunion personnalisés à partir de la page Stratégies de réunion, nous vous recommandons d’y accéder via des stratégies de personnalisation pour éviter la navigation via les stratégies par défaut de l’organisation globale.

Dans la stratégie de personnalisation de réunion, les administrateurs peuvent commencer à définir leur personnalisation en créant un thème de réunion.

Les thèmes de réunion hébergent les ressources suivantes pour votre thème :

- Logo : image du logo de votre organisation.
- Image personnalisée : image de marque de votre organisation (les images personnalisées ne sont pas [identiques aux arrière-plans de réunion personnalisés](custom-meeting-backgrounds.md)).
- Couleur personnalisée : il est recommandé d’utiliser la couleur primaire ou secondaire de votre marque, quelle que soit la couleur qui correspond le mieux à votre image de marque et à votre logo.

Pour créer un thème, sélectionnez **Ajouter un thème de réunion**.

### <a name="adding-a-custom-logo-image"></a>Ajout d’une image de logo personnalisée

Réunions Teams prend en charge les logos carrés qui s’affichent sur les surfaces clés pendant votre réunion, y compris l’écran de salle d’attente. Les images de logo doivent respecter les ratios de contraste d’accessibilité Microsoft (4:5:1).

Les chargements doivent respecter les paramètres suivants. Un administrateur peut uniquement charger :

- Formats d’image PNG et JPEG pour leur logo.
- Image de logo d’une taille maximale de 5 Mo.
- Images de logo avec une dimension minimale de 576 px x 576 px.
- Une seule image par thème à partir de leur appareil.

### <a name="adding-a-custom-image"></a>Ajout d’une image personnalisée

Les réunions Teams prennent en charge les images d’une organisation qui peauxent l’écran des réunions et fournissent une toile de fond colorée à vos réunions.

> [!NOTE]
> Ces images ne sont pas [identiques aux arrière-plans de réunion personnalisés](custom-meeting-backgrounds.md)

Les images personnalisées doivent respecter les ratios de contraste d’accessibilité Microsoft (4:5:1), et les chargements doivent suivre ces paramètres :

- Administration pouvez uniquement charger des formats d’image PNG et JPEG pour l’image de marque
- Administration pouvez uniquement charger une image de marque avec une taille maximale de 5 Mo
- Administration pouvez charger une image de marque avec les dimensions suivantes :
  - Dimensions minimales : 360 px X 360 px
  - Dimensions maximales : 2048 px X 2048 px
- Administration pouvez charger un minimum de 0 et un maximum d’une image par thème à partir de leur appareil

### <a name="adding-a-custom-color"></a>Ajout d’une couleur personnalisée

Les réunions Teams prennent en charge la couleur principale ou secondaire d’une organisation dans l’expérience de réunion. Vous pouvez entrer la valeur de code hexadécimal de la couleur de votre organisation, qui apparaîtra sur les surfaces clés de l’expérience de réunion.

> [!NOTE]
> Pour prendre en charge les normes d’accessibilité Microsoft, la couleur finale générée peut ne pas correspondre à la couleur de votre marque.

### <a name="previewing-a-meeting-theme"></a>Aperçu d’un thème de réunion

Une fois que vous avez ajouté vos ressources de réunion, vous pouvez afficher un aperçu de l’apparence de votre thème avant de l’enregistrer.  Si vous sélectionnez **Aperçu** , la boîte de dialogue d’aperçu s’ouvre et affiche le thème nouvellement défini pour le bureau et les appareils mobiles.

### <a name="save-meeting-theme"></a>Enregistrer le thème de réunion

En sélectionnant **Enregistrer**, le thème de la réunion est automatiquement enregistré et appliqué à vos réunions. Si vous sélectionnez **Enregistrer et appliquer pour ultérieurement** , vous enregistrez le thème de la réunion, mais ne l’appliquez à aucune de vos réunions. Pour appliquer ce thème, sélectionnez **Enregistrer** sur le créateur du thème de réunion ou utilisez le bouton bascule **Actuellement actif** dans la table de thème de réunion de la page stratégie de personnalisation.



### <a name="assigning-a-meeting-customization-policy-to-users"></a>Affectation d’une stratégie de personnalisation de réunion aux utilisateurs

Les stratégies de personnalisation de réunion peuvent être affectées à un, plusieurs ou à un groupe d’utilisateurs prédéfini dans votre locataire. Assurez-vous que ces utilisateurs disposent d’une licence Teams Premium pour utiliser ces fonctionnalités.

- Par défaut, tous les utilisateurs sous licence obtiennent la stratégie par défaut globale qui leur est affectée.
- Les stratégies de personnalisation personnalisées remplacent la valeur par défaut globale
- Un utilisateur sous licence ne peut se voir attribuer qu’une seule stratégie de personnalisation

### <a name="use-cases-for-multiple-departments-or-business-units-in-one-tenant"></a>Cas d’usage pour plusieurs services ou unités commerciales dans un seul locataire

Certaines organisations ont plusieurs unités commerciales sous différentes identités de marque au sein du même locataire. Dans ce cas, les administrateurs peuvent créer des stratégies de personnalisation de réunion dédiées à chaque marque. Ils peuvent également affecter un groupe d’utilisateurs d’un service ou d’une unité commerciale à une stratégie spécifique.

#### <a name="a-use-case"></a>Un cas d’usage

Contoso Ltd. a un seul locataire dans Microsoft Teams, qui contient les profils utilisateur de tous ses employés dans différentes organisations commerciales. L’entreprise cherche à adopter des réunions personnalisées dans Teams pour augmenter la présence de sa marque auprès de ses clients et encourager une culture d’entreprise interne.

Contoso a deux unités commerciales sous son organisation : Contoso Technical Services et Contoso Éducation. Les deux unités de référence ont leur propre image de marque distincte et souhaitent afficher leur marque lors de leurs réunions internes et externes.

Pour prendre en charge ce cas d’usage, les administrateurs de locataire peuvent créer deux stratégies de personnalisation distinctes :

- Stratégie A - Contoso Technical Services : contient le logo, l’image et la couleur de la marque Contoso Technical Service
- Stratégie B - Contoso Éducation : contient le logo, l’image et la couleur de la marque Contoso Education

Ils peuvent continuer à affecter les employés sous licence des services techniques Contoso à la stratégie A et les employés sous licence de Contoso Éducation à la stratégie B.

## <a name="where-are-meeting-themes-visible"></a>Où les thèmes de réunion sont-ils visibles ?

Clients pris en charge :

- Client de bureau 
- Android (versions 11 et ultérieures uniquement)
- iOS

|         | lanceur de participation | Pré-participation à la réunion | Salle d’attente de la réunion | Phase de réunion |
| :---:          |     :---:      |         :---:  |         :---:  |         :---:  |
| **Logo**   | Non | Oui| Oui| Oui|
| **Image**     | Non | Oui| Oui| Oui|
| **Couleur**     | Oui | Oui| Oui| Oui|

Les logos et images seront disponibles pour Join Launcher dans les futures mises à jour.
> [!NOTE]
> La nouvelle expérience de webinaire utilisera ces fonctionnalités de thème dans les réunions. La page d’inscription au webinaire sera toujours utilisée pour configurer la personnalisation du webinaire pour l’inscription aux réunions et les e-mails. Les organisateurs de réunions peuvent désactiver les thèmes de réunion d’un webinaire en optant pour les options de réunion. En savoir plus sur [la nouvelle expérience de webinaire](set-up-webinars.md)

### <a name="who-can-view-a-meeting-theme"></a>Qui peut afficher un thème de réunion

Bien que seuls les utilisateurs sous licence auxquels une stratégie de personnalisation de réunion soit affectée peuvent créer des réunions prenant en charge les thèmes de réunion, tout le monde peut afficher les thèmes appliqués à une réunion. Ces utilisateurs sont les suivants :

- Utilisateurs sous licence dans le locataire, Teams Premium
- Utilisateurs non titulaires d’une licence dans le locataire
- Invité des utilisateurs du locataire
- Utilisateurs externes
- Utilisateurs anonymes

### <a name="how-to-turn-off-meeting-themes-for-a-meeting"></a>Comment désactiver les thèmes de réunion pour une réunion

Les administrateurs de locataire peuvent autoriser les organisateurs de réunion à désactiver les thèmes de réunion pour une instance de réunion spécifique. La désactivation des thèmes de réunion renverra la réunion au thème Teams par défaut.

Pour permettre aux organisateurs de la réunion de désactiver les thèmes de réunion :

1. Accédez à la **stratégie de personnalisation de la réunion**.
1. Activez le paramètre **« Thème de réunion » qui permet aux organisateurs de désactiver le thème de la réunion pour des réunions spécifiques**.

Les organisateurs de réunion peuvent désactiver les thèmes de réunion en :

1. Accédez au menu **Options de réunion** pour une instance de réunion.
1. Désactivation de l’option de réunion **Autoriser les organisateurs à désactiver le thème de la réunion**.

> [!NOTE]
>
> - Pour les réunions ou séries périodiques, l’option de réunion s’applique à chaque instance de la réunion.
> - Les thèmes de réunion ne sont pas désactivés pour les réunions en cours. Pour appliquer des modifications, vous devez mettre fin à l’appel et redémarrer la réunion.

## <a name="best-practices-for-meeting-themes"></a>Bonnes pratiques pour les thèmes de réunion

- Utilisez uniquement les ressources d’image officielles de votre organisation. N’utilisez pas de contenu d’image qui ne vous appartient pas.
- Collaborez avec votre équipe de marque et de marketing pour vous assurer que vos ressources et couleurs d’image respectent les directives de votre organisation en matière de marque.
- Veillez à utiliser des images de logo de haute qualité, visibles sur les appareils petits et grands écrans.
- Les couleurs générées dans l’application Teams peuvent différer des couleurs de votre marque. Ce processus a été créé pour s’assurer que les normes d’accessibilité Microsoft sont respectées.
- Les utilisateurs disposant de paramètres d’appareil à contraste élevé ne verront pas les thèmes de réunion.

### <a name="accessibility"></a>Accessibilité

Voici quelques points pour vous assurer que les exigences d’accessibilité sont remplies :

- Suivez les modèles et la structure d’interface utilisateur existants : la structure et le texte actuels à l’écran ne sont pas modifiés avec cette fonctionnalité.
- Ratio de contraste d’image : les ressources d’image sont requises pour respecter le rapport de contraste des couleurs 4:5:1.  
- Prise en charge de la génération de couleurs accessibles : nous calculons la sortie de couleur accessible qui est la correspondance la plus proche de l’entrée de couleur de la marque tout en conservant les normes d’accessibilité Microsoft  
- Prise en charge du contraste élevé : pour les utilisateurs avec des paramètres de contraste élevé activés, la personnalisation ne s’applique pas. Ils continueront à voir l’expérience de réunion Teams par défaut.
- Contrôles Administration informatiques : les administrateurs informatiques peuvent empêcher les utilisateurs ayant des problèmes d’accessibilité de voir la personnalisation en : 
  - Contrôle de stratégie : vérifiez qu’elles ne sont pas ajoutées à une stratégie de personnalisation. Ce contrôle les empêche de créer des réunions avec personnalisation.
  - Options de réunion : les organisateurs de réunion peuvent désactiver la personnalisation d’une réunion si un utilisateur ayant des problèmes d’accessibilité rejoint la réunion.
