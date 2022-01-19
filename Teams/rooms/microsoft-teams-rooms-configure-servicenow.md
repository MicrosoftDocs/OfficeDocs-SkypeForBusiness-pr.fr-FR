---
title: Configurer ServiceNow pour salles Teams
author: cazawideh
ms.author: czawideh
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: En savoir plus sur la configuration de ServiceNow dans le portail salles Teams Premium’entreprise
f1keywords: ''
ms.openlocfilehash: deca4f8111dec958b19d9a6fa2651fca34f4050f
ms.sourcegitcommit: 9caa3131e9896b140afe10edea2b1e599eacd02b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2022
ms.locfileid: "62082210"
---
# <a name="configure-servicenow-for-teams-rooms"></a>Configurer ServiceNow pour salles Teams

Cet article décrit les conditions préalables et les étapes nécessaires à la configuration de votre environnement ServiceNow dans le salles Teams Premium web.

## <a name="before-you-begin"></a>Avant de commencer

### <a name="teams-rooms-prerequisites"></a>salles Teams conditions préalables

- Un rôle d’administrateur de service doit vous être attribué. Pour plus d’informations, voir [Contrôle d’accès en fonction du rôle avec Salles Microsoft Teams services gérés.](microsoft-teams-rooms-premium-rbac.md)

### <a name="servicenow-prerequisites"></a>Conditions préalables à ServiceNow

- Une inscription d’autorisation de base ou une inscription [OAuth.](https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/security/concept/c_OAuthApplications.html) Pour plus d’informations, voir [Créer des informations d’identification](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/servicenow_application_developer/app_store_learnv2_rest_rome_creating_credentials) dans ServiceNow.
- A ServiceNow instance and its instance host name and API URI
- Rôle d’un incident_manager supérieur ou supérieur
- Version logicielle de ServiceNow qui prend en charge l’API Table

## <a name="configure-your-environment"></a>Configurer votre environnement

La configuration de votre environnement est hautement personnalisable et dépend des besoins de votre organisation. Les étapes suivantes duivent comment copier votre configuration existante dans ServiceNow vers le salles Teams Premium web.

1. Ouvrez l’instance ServiceNow que vous voulez copier. Vous devrez vous y référencé lorsque vous remplirez le formulaire de configuration dans le salles Teams Premium’équipe.
2. Dans un nouvel onglet de navigateur, allez sur le [portail salles Teams Premium’équipe,](https://portal.rooms.microsoft.com/) puis sur **Paramètres.** Ensuite, sélectionnez **ServiceNow** dans le menu de navigation gauche pour ouvrir le formulaire de configuration.
3. Sélectionnez une méthode d’authentification pour vous connectez et entrez votre hôte ServiceNow Instance et votre URI d’API.
4. Tous les éléments requis dans la colonne Champ ServiceNow de la section Mappage des champs doivent être pré-remplis. Le tableau ci-dessous contient chaque champ ServiceNow et les valeurs correspondantes Salles Microsoft Teams champ. Terminez l’action pour chaque ligne de la section Mappage des champs. Pour les définitions de chaque champ ServiceNow, voir [Définitions de champ ServiceNow.](#servicenow-field-definitions)

| Champ ServiceNow | Salles Microsoft Teams champ | Action |
| --- | --- | --- |
| short_description | Description de l’incident | Aucune action n’est requise. La salles Teams de champ est remplie automatiquement. |
| description | Premier message | Aucune action n’est requise. La salles Teams de champ est remplie automatiquement. |
| assignment_group | Groupe de salles | Copiez la assignment_group dans votre instance ServiceNow et collez-la dans le champ de valeur ServiceNow du formulaire de configuration. Si vous avez plusieurs assignment_group, sélectionnez Ajouter un groupe **de salles** pour chaque valeur personnalisée supplémentaire. |
| gravité | Anneaux | La gravité est une valeur personnalisée dans ServiceNow. Il s’agit du quatrième élément dans la deuxième colonne de votre instance ServiceNow. Copiez la valeur et collez-la dans le champ de valeur ServiceNow dans le formulaire de configuration. Si vous avez plusieurs valeurs de gravité, sélectionnez **Ajouter un anneau** pour chaque valeur personnalisée supplémentaire. |
| Commentaires (facultatif) | Valeur personnalisée* | Pour ajouter un champ Commentaires au formulaire de configuration, **sélectionnez Ajouter** en haut de la section de mappage de champ. Copiez la valeur de commentaire dans votre instance ServiceNow et collez-la dans le champ ServiceNow du formulaire de configuration. Attribuez-lui un Microsoft Teams Salle dans le menu déroulant, puis copiez-collez la valeur ServiceNow. |
| état (résolu) | Valeur personnalisée* | Copiez l’état de résolution de votre instance ServiceNow et collez-la dans le champ de valeur ServiceNow dans le formulaire de configuration. |
| close_code | Valeur personnalisée* | Dans **l’onglet Informations de** résolution de votre instance ServiceNow, copiez le code de fermeture et collez-le dans le champ de valeur ServiceNow dans le formulaire de configuration. |

*Sélectionner des valeurs personnalisées dans le menu déroulant

>[!NOTE]
>Si vous ne trouvez pas vos valeurs personnalisées, contactez votre administrateur ServiceNow.

Pour ajouter d’autres champs obligatoires à la section Résoudre l’incident, sélectionnez **Ajouter.**

## <a name="test-and-enable"></a>Tester et activer

Après avoir complété le formulaire de configuration, **sélectionnez Test** au bas de la page. Un test est nécessaire pour soumettre votre configuration.

Une fois votre test réussi, sélectionnez **Envoyer** pour enregistrer vos modifications. Lorsque vous êtes prêt à activer ServiceNow pour votre organisation, basculez le bouton bascule **Do you want to enable ServiceNow?** (Activer). 

## <a name="servicenow-field-definitions"></a>Définitions de champs ServiceNow

- **short_description**: Le champ de description court dans ServiceNow est une brève valeur alphanumérique de 160 caractères qui fournit un résumé de l’incident. Une courte description équivaut à la description de l’incident dans salles Teams Premium’entreprise.

- **description**: Le champ de description dans ServiceNow est la première valeur dans l’historique des conversations d’un incident ServiceNow. La description équivaut au Premier message du portail salles Teams Premium’équipe.

- **assignment_group**: Le champ de groupe d’affectations dans ServiceNow est utilisé pour organiser les incidents. Le groupe d’affectations est équivalent aux groupes de salles dans le salles Teams Premium’équipe. Par défaut, il existe un seul groupe de salles, et d’autres peuvent être ajoutés. Vous décidez du nombre de groupes qui s’y trouver et de la manière de grouper vos incidents. Par exemple, vous pouvez choisir d’organiser vos incidents par emplacement.

- **gravité :** Le champ gravité dans ServiceNow est utilisé pour organiser les incidents par priorité. Les valeurs qui désignent la priorité peuvent être personnalisées. La gravité est équivalente au champ Anneau dans le portail salles Teams Premium’équipe. Pour personnaliser les anneaux dans le salles Teams Premium de navigation, voir Mises **à** jour dans le menu de navigation gauche. Ensuite, sous **l’onglet Anneaux,** **sélectionnez Ajouter un anneau.**

- Commentaires est un champ facultatif dans ServiceNow utilisé pour inclure des champs **obligatoires personnalisés** de votre instance ServiceNow dans votre configuration salles Teams Premium portail. L’équivalent des commentaires est une valeur personnalisée dans le portail salles Teams Premium’équipe.

- **état (résolu)**: le champ État (résolu) dans ServiceNow est utilisé pour indiquer la façon dont un incident a été résolu et est requis pour fermer un incident. La valeur état (résolu) est personnalisable. L’équivalent de l’état (résolu) est une valeur personnalisée dans le portail salles Teams Premium’état.

- **close_code**: un code de fermeture doit être affecté à un incident une fois qu’il a été complètement résolu. Cette valeur est personnalisable dans ServiceNow. L’équivalent du code de fermeture est une valeur personnalisée dans le salles Teams Premium’entreprise.
