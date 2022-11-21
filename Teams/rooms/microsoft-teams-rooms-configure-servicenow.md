---
title: Configurer ServiceNow pour salles Teams
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: En savoir plus sur la configuration de ServiceNow dans le portail de gestion des Salles Teams Pro
f1keywords: ''
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
ms.openlocfilehash: 2166332df2c4ea388256d32a9dbc35a709042041
ms.sourcegitcommit: baf29d244b428712052553f9e4484e72e727247e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2022
ms.locfileid: "69046853"
---
# <a name="configure-servicenow-for-teams-rooms"></a>Configurer ServiceNow pour salles Teams

Cet article décrit les prérequis et les étapes à suivre pour configurer votre environnement ServiceNow dans le portail de gestion Salles Teams Pro.

## <a name="watch-microsoft-teams-rooms-pro-management--service-now-integration"></a>Regarder : Gestion Salles Microsoft Teams Pro — Intégration de Service Now

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4ZK4B]


### <a name="teams-rooms-prerequisites"></a>salles Teams prérequis

- Vous devez disposer d’un rôle Administrateur de service attribué. Pour plus d’informations, consultez [Contrôle d’accès en fonction du rôle avec Salles Microsoft Teams Pro Management](rooms-pro-rbac.md).

### <a name="servicenow-prerequisites"></a>Conditions préalables à ServiceNow

- Une connexion d’autorisation de base ou une connexion [OAuth](https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/security/concept/c_OAuthApplications.html) . Pour plus d’informations, consultez [Création d’informations d’identification](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/servicenow_application_developer/app_store_learnv2_rest_rome_creating_credentials) dans ServiceNow.
- Une instance ServiceNow et son nom d’hôte d’instance et son URI d’API
- Rôle incident_manager ou supérieur
- Une version logicielle de ServiceNow qui prend en charge l’API Table

## <a name="configure-your-environment"></a>Configurer votre environnement

La façon dont votre environnement est configuré est hautement personnalisable et dépend des besoins de votre organisation. Les étapes suivantes expliquent comment copier votre configuration existante dans ServiceNow dans le portail de gestion Salles Teams Pro.

1. Ouvrez l’instance ServiceNow que vous souhaitez copier. Vous devez y faire référence lorsque vous remplissez le formulaire de configuration dans le portail de gestion Salles Teams Pro.
2. Dans un nouvel onglet de navigateur, accédez au [portail de gestion Salles Teams Pro](https://portal.rooms.microsoft.com/) et accédez à **Paramètres**. Ensuite, sélectionnez **ServiceNow** dans le menu de navigation de gauche pour ouvrir le formulaire de configuration.
3. Sélectionnez une méthode d’authentification pour vous connecter et entrez votre HÔTE d’instance ServiceNow et l’URI d’API.
4. Tous les éléments requis dans la colonne Champ ServiceNow de la section Mappage de champs doivent être préremplis. Le tableau ci-dessous contient chaque champ ServiceNow et son champ Salles Microsoft Teams correspondant. Effectuez l’action pour chaque ligne de la section Mappage de champs. Pour obtenir les définitions de chaque champ ServiceNow, consultez [Définitions de champs ServiceNow](#servicenow-field-definitions).

| Champ ServiceNow | champ Salles Microsoft Teams | Action |
| --- | --- | --- |
| short_description | Description de l’incident | Aucune action n’est nécessaire. Le champ salles Teams est rempli automatiquement. |
| Description | Premier message | Aucune action n’est nécessaire. Le champ salles Teams est rempli automatiquement. |
| assignment_group | Groupe de salles | Copiez la valeur assignment_group dans votre instance ServiceNow et collez-la dans le champ valeur ServiceNow du formulaire de configuration. Si vous avez plusieurs assignment_group, sélectionnez **Ajouter un groupe de salles** pour chaque valeur personnalisée supplémentaire. |
| Gravité | Anneaux | La gravité est une valeur personnalisée dans ServiceNow. Il s’agit du quatrième élément de la deuxième colonne de votre instance ServiceNow. Copiez la valeur et collez-la dans le champ valeur ServiceNow du formulaire de configuration. Si vous avez plusieurs valeurs de gravité, sélectionnez **Ajouter un anneau** pour chaque valeur personnalisée supplémentaire. |
| Commentaires (facultatif) | Valeur personnalisée* | Pour ajouter un champ de commentaires au formulaire de configuration, sélectionnez **Ajouter** en haut de la section mappage de champs. Copiez la valeur du commentaire dans votre instance ServiceNow et collez-la dans le champ ServiceNow dans le formulaire de configuration. Affectez-lui un champ Salle Microsoft Teams dans le menu déroulant, puis copiez et collez la valeur ServiceNow. |
| état (résolu) | Valeur personnalisée* | Copiez l’état de résolution de votre instance ServiceNow et collez-le dans le champ de valeur ServiceNow du formulaire de configuration. |
| close_code | Valeur personnalisée* | Sous l’onglet **Informations de résolution** de votre instance ServiceNow, copiez le code de fermeture et collez-le dans le champ de valeur ServiceNow dans le formulaire de configuration. |

*Sélectionner des valeurs personnalisées dans le menu déroulant

>[!NOTE]
>Si vous ne trouvez pas vos valeurs personnalisées, contactez votre administrateur ServiceNow.

Pour ajouter des champs obligatoires supplémentaires à la section Résoudre l’incident, sélectionnez **Ajouter**.

## <a name="test-and-enable"></a>Tester et activer

Après avoir rempli le formulaire de configuration, sélectionnez **Tester** en bas de la page. Un test est nécessaire pour envoyer votre configuration.

Une fois votre test réussi, sélectionnez **Envoyer** pour enregistrer vos modifications. Une fois que vous êtes prêt à activer ServiceNow pour votre organisation, basculez le bouton bascule **Voulez-vous activer ServiceNow ?** sur **Activé**.

## <a name="servicenow-field-definitions"></a>Définitions de champ ServiceNow

- **short_description** : le champ de description courte dans ServiceNow est une brève valeur alphanumérique de 160 caractères qui fournit un résumé de l’incident. Une brève description équivaut à la description de l’incident dans le portail de gestion Salles Teams Pro.

- **description** : le champ description dans ServiceNow est la première valeur de l’historique des conversations d’un incident ServiceNow. Description équivaut au premier message dans le portail de gestion Salles Teams Pro.

- **assignment_group** : le champ de groupe d’affectation dans ServiceNow est utilisé pour organiser les incidents. Les groupes d’affectations sont équivalents aux groupes de salles dans le portail de gestion Salles Teams Pro. Par défaut, il existe un groupe de salles, et d’autres peuvent être ajoutés. Vous décidez du nombre de groupes et de la façon de regrouper vos incidents. Par exemple, vous pouvez choisir d’organiser vos incidents par emplacement.

- **gravité** : le champ gravité dans ServiceNow est utilisé pour organiser les incidents par priorité. Les valeurs qui désignent la priorité sont personnalisables. La gravité équivaut au champ Anneau dans le portail de gestion Salles Teams Pro. Pour personnaliser les anneaux dans le portail de gestion Salles Teams Pro, accédez à **Mises à jour** dans le menu de navigation de gauche. Ensuite, accédez à l’onglet **Anneaux** et sélectionnez **Ajouter une bague**.

- **commentaires** : Commentaires est un champ facultatif dans ServiceNow qui est utilisé pour inclure des champs requis personnalisés de votre instance ServiceNow dans votre configuration du portail de gestion Salles Teams Pro. L’équivalent des commentaires est une valeur personnalisée dans le portail de gestion Salles Teams Pro.

- **état (résolu)** : le champ état (résolu) dans ServiceNow est utilisé pour désigner la façon dont un incident a été résolu et est nécessaire pour fermer un incident. La valeur d’état (résolue) est personnalisable. L’équivalent de l’état (résolu) est une valeur personnalisée dans le portail de gestion Salles Teams Pro.

- **close_code** : un code de fermeture doit être affecté à un incident une fois qu’il est complètement résolu. Cette valeur est personnalisable dans ServiceNow. L’équivalent du code de fermeture est une valeur personnalisée dans le portail de gestion Salles Teams Pro.
