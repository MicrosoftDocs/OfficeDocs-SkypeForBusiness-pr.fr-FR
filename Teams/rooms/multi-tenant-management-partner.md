---
title: Gestion des clients multilocataires pour les partenaires
author: altsou
ms.author: altsou
ms.date: 07/25/2022
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Gestion des clients Mult-tenant pour les partenaires.
f1keywords: ''
ms.openlocfilehash: e4e89d483d15ad7f521afd9c0686b3d72ab9e09d
ms.sourcegitcommit: 64c01699022b47fdfec8dc6e2ca279e57eae3baa
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68243905"
---
# <a name="multi-tenant-customer-management-for-partners"></a>Gestion des clients multilocataires pour les partenaires

La gestion multilocataire (MTM) dans le service salles Teams Pro Management aide les organisations partenaires à gérer plusieurs clients au même endroit, avec leurs propres informations d’identification de domaine. Les utilisateurs partenaires voient uniquement les salles client qu’ils sont affectés à la gestion. Il est possible d’appliquer des rôles personnalisés pour chaque client dans le portail MTM, ce qui donne aux organisations partenaires un contrôle précis des autorisations sur les ressources du client. 

Le portail MTM est accessible via ce [lien](https://partner.rooms.microsoft.com/).

> [!Note] 
> Les organisations partenaires ne peuvent pas gérer leurs propres salles via le portail MTM. Ces salles peuvent être gérées dans le [portail de gestion Pro](https://portal.rooms.microsoft.com/). 

## <a name="pre-requisites-for-managing-your-customers-through-the-mtm-experience"></a>Conditions préalables à la gestion de vos clients via l’expérience MTM

Pour accéder au portail MTM, votre organisation doit être intégrée en tant que partenaire Elite pour MTR Pro Management. Pour devenir un contact partenaire Elite askelite@microsoft.com.

## <a name="on-boarding-customers"></a>Clients à bord

Pour gérer les clients via le portail Pro Management-MTM, une relation doit être établie entre le locataire de l’organisation partenaire et le client via une invitation envoyée par le client. 

## <a name="tenant-managers"></a>Gestionnaires de locataires

Ce rôle intégré est configurable uniquement dans le portail Pro Management-MTM. Ce rôle vous permet d’affecter un groupe d’utilisateurs qui acceptent des invitations, mais qui ne sont pas impliqués dans la gestion des salles client. Il est recommandé de configurer le rôle. Dans le cas contraire, seuls les utilisateurs disposant du rôle Administrateur du service géré dans votre locataire pourront accepter les invitations.

**Pour configurer les gestionnaires de locataires**
 
1.  Connectez-vous au portail Pro Management-MTM en tant qu’administrateur général ou administrateur du service géré.
2.  Accédez aux gestionnaires de locataires.
3.  Sélectionnez **Ajouter des gestionnaires de locataires**.
4.  Dans le volet d’informations, recherchez les utilisateurs ou les groupes de sécurité.
5.  Sélectionnez l’utilisateur ou le groupe.
6.  Sélectionnez **Ajouter**.

### <a name="invitation-from-the-customer"></a>Invitation du client

Le partenaire doit fournir le nom de domaine aux clients. Seuls les rôles Administrateur général, Administrateur de service géré et Gestionnaires de locataires peuvent voir et accepter l’invitation lorsqu’ils se connectent au portail Pro Management-MTM. 

> [!Note]
> Même si ces rôles peuvent voir des invitations et des métadonnées de locataire de haut niveau, vous ne verrez pas les données du client tant que vous n’avez pas reçu un rôle avec ce client.

Les détails de l’invitation du client sont décrits dans [la gestion multilocataire pour les clients](multi-tenant-management-customer.md).

**Pour accepter une invitation en attente**

1. Connectez-vous au portail Pro Management-MTM en tant qu’administrateur général, administrateur du service géré ou gestionnaire de locataires.
1. Accédez à **Locataires**.
1. Sélectionnez l’invitation affichée avec l’état « En attente ».
1. Passez en revue les détails de l’invitation.
1. Affectez des utilisateurs qui seront les principaux administrateurs de ce client.
1. Sélectionnez **Accepter** pour établir la relation partenaire-client.

   La sélection de **Refuser** supprime l’invitation.

   > [!Note]
   > Il n’existe aucune association permanente avec l’utilisateur qui accepte l’invitation.

   > [!Note]
   > *Si l’invitation est refusée accidentellement, le client doit créer une invitation.* 

**Pour passer en revue la configuration ou ajouter d’autres administrateurs principaux pour un locataire**

1. Sélectionnez le client dans la liste **des locataires** .
1. Dans le volet d’informations, sélectionnez **Administrateurs principaux**.
1. Recherchez l’utilisateur ou le groupe.
1. Sélectionnez **Ajouter** pour confirmer la sélection.

## <a name="off-boarding-customers"></a>Clients en dehors de l’embarquement

Pour déconnecter un client, vous devez le supprimer de la liste **des locataires** .

**Pour supprimer un client** 

1. Connectez-vous au portail Pro Management-MTM en tant qu’administrateur principal pour le client que vous souhaitez supprimer.
1. Accédez à **Locataires**.
1. Sélectionnez le client que vous souhaitez supprimer.
1. Dans le volet détails du client, **sélectionnez Supprimer le client**.
1. Sélectionnez **Supprimer** dans l’invite de confirmation pour mettre fin à l’association entre vous et le locataire client.

## <a name="managing-partner-roles"></a>Gestion des rôles de partenaire

Les rôles de partenaire permettent la délégation des responsabilités à un personnel supplémentaire. Le concept de ces rôles est le même que celui décrit dans le [contrôle d’accès en fonction du rôle](microsoft-teams-rooms-premium-rbac.md), mais dans le contexte de chaque client. En outre, il est important de noter que les rôles de partenaire sont distincts des rôles du client. Les rôles de partenaire peuvent être supprimés par le client. 

Le rôle **d’administrateur principal** est le seul rôle intégré pour chaque client intégré et dispose de presque toutes les autorisations , dans le contexte du client, pour le service Pro Management (voir le tableau 1). Les autorisations de rôle partenaire** s’étendent uniquement jusqu’aux salles désignées par le client. Par exemple, si le client est une organisation globale et affecte le partenaire pour gérer toutes les salles américaines, l’administrateur principal ne peut gérer et déléguer que les autorisations pour ces salles. Le partenaire n’a aucune visibilité sur les autres salles que le client peut avoir dans d’autres pays. 

**Pour gérer les utilisateurs dans le rôle **Partenaire** pour un client**

1. Accédez à **Paramètres > rôles**. 
1. Sélectionnez le client dans la liste déroulante pour laquelle vous souhaitez modifier le rôle de partenaire.
1. Sélectionnez le rôle intégré **Administrateurs principaux** dans la liste.
1. Sélectionnez **Affectations.**
1. Dans la liste, sélectionnez **Administrateurs affectés.**
1. Sélectionnez **Membres.**
1. Sélectionnez **Modifier.** 
1. Recherchez l’utilisateur ou le groupe de sécurité que vous souhaitez ajouter dans la barre de recherche.
1. Sélectionnez l’utilisateur ou le groupe.
1. Sélectionnez **Enregistrer** pour confirmer les modifications.

### <a name="managing-custom-partner-roles-for-a-customer"></a>Gestion des rôles de partenaires personnalisés pour un client

En tant que partenaire, vous pouvez créer des rôles personnalisés en fonction de vos besoins opérationnels. Par exemple, vous pouvez créer un rôle de support technique qui ne doit avoir que des autorisations de gestion des incidents. 

**Pour gérer les rôles**

1. Accédez à **Paramètres > rôles**. 
1. Sélectionnez le client dans le menu déroulant pour lequel vous souhaitez modifier le rôle de partenaire.
1. Créez un [rôle personnalisé](microsoft-teams-rooms-premium-rbac.md#built-in-roles).




|Fonctionnalité|Autorisation|**ADMINISTRATION MMR**|**Prospect de site**|**Site Tech**|**Administrateurs principaux**|
| :- | :- | :- | :- | :- | :- |
|Chambres|Afficher| &#10004;|&#10004;|&#10004;|&#10004;|
||Modifier|&#10004;|&#10004;|&#10004;|&#10004;|
||Réinitialiser la clé|&#10004;||||
||Clé de téléchargement|&#10004;|&#10004;|&#10004;||
||Désinscrire|&#10004;|&#10004;|&#10004;||
||Create |&#10004;|&#10004;|||
|Gestion de groupe|Afficher|&#10004;|&#10004;||&#10004;|
||Modifier|&#10004;|&#10004;|||
||Create |&#10004;|&#10004;|||
|Mettre à jour la gestion des anneaux|Afficher|&#10004;|&#10004;||&#10004;|
||Modifier|&#10004;|&#10004;||&#10004;|
|Rapports|Afficher|&#10004;|&#10004;||&#10004;|
||Créer un incident client|&#10004;|&#10004;|&#10004;|&#10004;|
|Gestion des tickets|Afficher|&#10004;|&#10004;|&#10004;|&#10004;|
||Mettre à jour|&#10004;|&#10004;|&#10004;|&#10004;|
|Paramètres MMR|Afficher|&#10004;||||
||Modifier|&#10004;||||
|Gestion des rôles|Afficher |&#10004;|||&#10004;|
||Modifier|&#10004;|||&#10004;|

> [!Note]
> Un utilisateur affecté en tant qu’administrateur principal pour le client A dispose des autorisations complètes dans le service Pro Management pour ce seul client. Les autorisations de l’utilisateur dans le client A n’ont aucune influence sur les autres clients.

## <a name="security"></a>Sécurité

Les clients finaux conservent le contrôle de l’accès à leurs données et peuvent supprimer complètement un partenaire ou des rôles spécifiques à tout moment.

Avec la fonctionnalité d’accès délégué, un partenaire n’obtient pas d’autres privilèges en dehors du portail de gestion Pro. Par exemple, en utilisant cette fonctionnalité pour inviter un partenaire à gérer des salles dans le portail de gestion Pro, aucune autorisation n’est accordée à AAD, au Centre de Administration Teams ou à tout autre produit Microsoft. En outre, les partenaires n’ont pas accès à l’affichage ou à la modification des salles non définies dans l’étendue de l’invitation.

Une fois que la relation entre le partenaire et le client est établie, comme décrit dans la section « Clients d’intégration » de ce document, le partenaire peut afficher les données de salle dans le portail Pro Management. Cela inclut toutes les données présentes dans le portail de gestion Pro, mais dérivées d’autres produits Microsoft. Par exemple, les rapports de qualité des appels dans le portail Pro Management sont dérivés des données de qualité des appels Teams.

Les données résident dans le locataire du client et ne sont pas copiées vers le locataire du partenaire. 

Le portail MTM utilise l’authentification AAD pour valider les informations d’identification de connexion du partenaire. Il est important de noter qu’à ce stade, les stratégies d’authentification du client ne s’appliqueront pas au partenaire. Par exemple, si le client a une stratégie d’authentification multifacteur, elle ne se traduit pas par le partenaire.

Le client peut extraire les journaux d’audit pour le portail Pro Management, qui inclut l’activité du partenaire. Consultez [la journalisation d’audit dans le service managé salles Teams](multi-tenant-auditing.md).

> [!Note]
> L’audit AAD et l’audit O365 ne capturent pas les journaux à partir du portail de gestion Pro.

## <a name="navigating-the-mtm-portal"></a>Navigation dans le portail MTM

Le portail MTM propose deux modèles interactifs pour naviguer entre les données client :

- Agréger des vues où les données de tous vos clients sont consolidées dans une liste unique et peuvent être filtrées.

  > [!Note]
  > Cette vue est prise en charge uniquement dans la page **Incidents** lorsque **l’option Activer tous les tickets** est activée.
  >
  > ![Figure 1](../media/multi-tenant-management-partner-001.png)

 - Changement de locataire où seules les données du **client** sélectionnées dans la liste déroulante s’affichent.
