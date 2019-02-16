---
title: Présentation de l’appartenance dynamique pour les équipes
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Découvrez les membres de l’équipe dynamique en fonction DAS.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fe6a097ba413c81d90f5fe519c5d6cbf1377a98
ms.sourcegitcommit: 2ef6a05c659100eea0d92c729001cd4e14434b9f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2019
ms.locfileid: "30062654"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Présentation de l’appartenance dynamique pour les équipes

Teams Microsoft prend en charge les équipes associées aux groupes de Office 365 à l’aide de membres dynamiques. Membres dynamiques permet l’appartenance d’une équipe à être définis par une ou plusieurs règles qui vérifient pour certains attributs de l’utilisateur dans Azure Active Directory (DAS). Les utilisateurs sont automatiquement ajoutées ou supprimées pour les équipes corrects que modifier les attributs de l’utilisateur ou les utilisateurs rejoignent ou quittent de client.

Avec appartenance dynamique, que vous pouvez le programme d’installation des équipes pour certaines cohortes d’utilisateurs dans votre organisation. Les scénarios possibles sont les suivantes :
- Un hôpital peut créer des équipes distinctes pour personnel, les médecins et chirurgiens de diffuser des communications. Ceci est particulièrement important si l’hôpital repose sur les employés temp.
- Une université peut créer une équipe pour tous les enseignants au sein d’une université particulier, y compris une faculté auxiliaire du qui change fréquemment.
- Une compagnie souhaite créer une équipe pour chaque vol (par exemple une mardi MIDI sans interruption de Chicago à Atlanta) et disposer d’une équipe de vol régulièrement modifié automatiquement affectées ou supprimés selon les besoins.

À l’aide de cette fonctionnalité, mise à jour des membres d’une équipe donnée automatiquement selon un ensemble spécifique de critères, au lieu de gérer manuellement les appartenances. Cela nécessite des licences d’Azure AD Premium P1 et l’appartenance de l’équipe peut être [attribué par un administrateur du client](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) pour les propriétés de l’utilisateur DAS à condition qu’un client et un compte d’administrateur. 

Microsoft Teams peut prendre de quelques minutes à 2 heures pour refléter les modifications d’appartenance dynamique une fois qu’ils prennent effet dans le groupe d’Office 365 pour une équipe. 

> [!NOTE]
> - Les règles peuvent définir, qui est un membre d’équipe, mais qui n’est pas une propriétaire de l’équipe.
> - Les limites en cours sur la taille de l’équipe et de canal, voir [limites et les spécifications pour les équipes Microsoft](limits-specifications-teams.md) .
> - Propriétaires ne sera pas en mesure d’ajouter ou supprimer des utilisateurs en tant que membres de l’équipe, étant donné que les membres sont définis par les règles de groupe dynamique.
> - Les membres ne pourront pas de laisser les équipes soutenues par groupes dynamiques.


## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a>Création et gestion d’un groupe d’Office 365 avec appartenance dynamique
En étant connecté le client d’administration, suivez les instructions de [Création d’un groupe dynamique et de vérifier l’état](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule). Selon vos besoins, font référence aux [règles de membres dynamiques pour les groupes dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).

## <a name="create-a-new-team-with-your-o365-group"></a>Créer une nouvelle équipe avec votre groupe O365

Attendez que les modifications d’appartenance prennent effet maintenant et créer une nouvelle équipe comme décrit dans les [groupes d’améliorer existant Office 365 avec les équipes Microsoft](enhance-office-365-groups.md).

## <a name="apply-dynamic-membership-to-an-existing-team"></a>Appliquer l’appartenance dynamique à une équipe existante

Vous pouvez également prendre une équipe existante et modifier pour avoir une appartenance dynamique, comme décrit dans [Modifier l’appartenance au groupe statique dynamique dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).

## <a name="changes-in-client-behavior"></a>Changements de comportement du client

Une fois que l’appartenance dynamique est activé pour une équipe, les clients équipes n’autorise plus gestion des membres de l’équipe. Toutes les options pour ajouter des membres, modifier des rôles, envoyer approuver les demandes de participation et laissez l’équipe sont masquées.
