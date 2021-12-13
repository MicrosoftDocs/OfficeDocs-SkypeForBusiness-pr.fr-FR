---
title: Gestion client multi-client pour les partenaires
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Gestion du client client Mult pour les partenaires.
f1keywords: ''
ms.openlocfilehash: 5ce4493ef9a5e6c959bf10c600c2b9697129d9df
ms.sourcegitcommit: 4095a1d5e507ac5cb23ed17611c1fbd4b744b23f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/13/2021
ms.locfileid: "61420204"
---
# <a name="multi-tenant-customer-management-for-partners"></a>Gestion client multi-client pour les partenaires

La gestion multi tenante (MTM) dans le service salles Teams géré (TRM) permet aux organisations partenaires de gérer plusieurs clients au même endroit, avec leurs propres informations d’identification de domaine. Les utilisateurs partenaires ne peuvent voir que les salles des clients qu’ils sont chargés de gérer. Il est possible d’appliquer des rôles personnalisés pour chaque client du client MTM, ce qui donne aux organisations partenaires un contrôle plus explicite des autorisations sur les ressources du client. 

Le portail MTM est accessible via ce [lien.](https://partner.rooms.microsoft.com/)

> [!Note] 
> Les organisations partenaires ne peuvent pas gérer leurs propres salles via le portail MTM. Ces salles peuvent être gérées dans le [portail TRM.](https://portal.rooms.microsoft.com/) 

## <a name="pre-requisites-for-managing-your-customers-through-the-mtm-experience"></a>Conditions préalables à la gestion de vos clients via l’expérience MTM

Pour accéder au portail MTM, votre organisation doit être intégré en tant que partenaire Elite pour le service TRM. Pour devenir un partenaire Elite, askelite@microsoft.com.


## <a name="on-boarding-customers"></a>Nouveaux clients à l’équipe

Pour gérer les clients via le portail TRM-MTM, une relation doit être établie entre le client de l’organisation partenaire et le client via une invitation envoyée par le client. 

### <a name="invitation-from-the-customer"></a>Invitation du client

Le partenaire fournit les noms des principes utilisateurs (UPN) des utilisateurs qui seront administrateurs principaux attribués au client. Seuls les utilisateurs identifiés dans l’invitation peuvent voir et accepter l’invitation lorsqu’ils se connectent au portail TRM-MTM. 

> [!Note]
> Même si vous avez des privilèges élevés tels que l’administrateur général, vous ne verrez pas l’invitation, sauf si vous y êtes explicitement ajouté. 

Les détails de l’invitation client sont décrits dans la gestion [de plusieurs clients pour les clients.](multi-tenant-management-customer.md)

**Pour accepter une invitation en attente**

1. Connectez-vous au portail TRM-MTM en tant qu’un des utilisateurs sur l’invitation.
1. Go to **Customers.**
1. Sélectionnez l’invitation affichant le statut « En attente ».
1. Examinez les détails de l’invitation.
1. Sélectionnez **Accepter** pour établir la relation client-partenaire.

   La sélection **Refuser supprime** l’invitation que l’utilisateur refuse. L’invitation est toujours disponible pour les autres utilisateurs qui n’ont pas encore fait cela.

   > [!Note]
   > L’invitation est unique et indépendante pour chaque utilisateur. Le premier utilisateur à accepter établit le lien entre le partenaire et le client. Il n’existe aucune association permanente avec l’utilisateur qui établit le lien. Les utilisateurs suivants qui acceptent l’invitation sont ajoutés en tant qu’administrateurs principaux.

   > [!Note]
   > *Si un utilisateur partenaire refuse accidentellement l’invitation, il est préférable qu’un autre utilisateur l’ajoute simplement au rôle de partenaire (ou à tout autre rôle RBAC) pour ce client.* 

Après avoir accepté l’invitation, l’utilisateur est automatiquement ajouté en tant qu’administrateur principal du client de ce client. 

Pour examiner la configuration de ce client, sélectionnez-le dans la **liste de** clients.


## <a name="off-boarding-customers"></a>Les clients sont en fin de vie

Pour dé-utiliser un client, vous devez le supprimer de la liste de clients.

**Pour supprimer un client** 

1. Connectez-vous au portail TRM-MTM en tant qu’administrateur principal du client que vous souhaitez supprimer.
1. Go to **Customers.**
1. Sélectionnez le client que vous souhaitez supprimer.
1. Dans le volet Détails du client, sélectionnez **Supprimer le client.**
1. Sélectionnez **Supprimer** dans l’invite de confirmation pour mettre fin à l’association entre votre client et le client.


## <a name="managing-partner-roles"></a>Gestion des rôles de partenaire

Les rôles de partenaire permettent la délégation des responsabilités au personnel supplémentaire. Le concept de ces rôles est identique à celui décrit dans le contrôle d’accès en fonction du [rôle,](microsoft-teams-rooms-premium-rbac.md)mais dans le contexte de chaque client. De plus, il est important de noter que les rôles de partenaire sont différents des rôles du client. Les rôles de partenaire peuvent être supprimés par le client. 

Le  rôle d’administrateur principal est le seul rôle intégré pour chaque client intégré et dispose de presque toutes les autorisations (dans le contexte du client) pour le service TRM (voir le tableau 1). Les autorisations de rôle partenaire** s’étendent uniquement jusqu’aux salles désignées par le client. Par exemple, si le client est une organisation mondiale et affecte au partenaire la gestion de toutes les salles américaines, l’administrateur principal ne peut gérer et déléguer les autorisations de ces salles. Le partenaire n’a aucune visibilité sur les autres salles que peut avoir le client dans d’autres pays. 

> [!Important]
> Le rôle Administrateur **principal** doit toujours être au moins un utilisateur.

**Pour gérer les utilisateurs dans **le rôle partenaire** d’un client**

1. Go to **Paramètres > Roles.** 
1. Sélectionnez le client dans la liste modifiable pour laquelle vous souhaitez modifier le rôle de partenaire.
1. Sélectionnez **le rôle intégré Administrateurs primaires** dans la liste.
1. Sélectionnez **Devoirs.**
1. Dans la liste, sélectionnez **Administrateurs invités.**
1. Sélectionnez **Membres.**
1. Cliquez sur **Sélectionner Modifier.** 
1. Recherchez l’utilisateur ou le groupe de sécurité que vous souhaitez ajouter dans la barre de recherche.
1. Sélectionnez l’utilisateur ou le groupe.
1. Cliquez sur **Enregistrer pour** confirmer les modifications.

### <a name="managing-custom-partner-roles-for-a-customer"></a>Gestion des rôles de partenaire personnalisés pour un client

En tant que partenaire, vous pouvez créer des rôles personnalisés pour répondre à vos besoins opérationnels. Par exemple, vous pouvez créer un rôle de service d’aide qui ne doit avoir que des autorisations de gestion des incidents. 

**Pour gérer les rôles**

1. Go to **Paramètres > Roles.** 
1. Sélectionnez le client dans la drop-down pour laquelle vous souhaitez modifier le rôle de partenaire.
1. Créer un [rôle personnalisé.](microsoft-teams-rooms-premium-rbac.md#built-in-roles)




|Fonctionnalité|Autorisation|**Administrateur MMR**|**Chef de site**|**Site Tech**|**Administrateurs principaux**|
| :- | :- | :- | :- | :- | :- |
|Salles|Afficher| &#10004;|&#10004;|&#10004;|&#10004;|
||Modifier|&#10004;|&#10004;|&#10004;|&#10004;|
||Réinitialiser la touche|&#10004;||||
||Clé de téléchargement|&#10004;|&#10004;|&#10004;||
||Désinscrire|&#10004;|&#10004;|&#10004;||
||Create |&#10004;|&#10004;|||
|Gestion de groupe|Afficher|&#10004;|&#10004;||&#10004;|
||Modifier|&#10004;|&#10004;|||
||Create |&#10004;|&#10004;|||
|Mettre à jour la gestion de l’anneau|Afficher|&#10004;|&#10004;||&#10004;|
||Modifier|&#10004;|&#10004;||&#10004;|
|Rapports|Afficher|&#10004;|&#10004;||&#10004;|
||Créer un incident client|&#10004;|&#10004;|&#10004;|&#10004;|
|Gestion des tickets|Afficher|&#10004;|&#10004;|&#10004;|&#10004;|
||Mettre à jour|&#10004;|&#10004;|&#10004;|&#10004;|
|MmR Paramètres|Afficher|&#10004;||||
||Modifier|&#10004;||||
|Gestion de rôle|Afficher |&#10004;|||&#10004;|
||Modifier|&#10004;|||&#10004;|

> [!Note]
> Un utilisateur assigné en tant qu’administrateur principal du client A dispose des autorisations complètes dans le service TRM uniquement pour ce client. Les autorisations de l’utilisateur dans le client A n’ont aucune influence sur les autres clients.

## <a name="security"></a>Sécurité

Les clients finux conservent le contrôle de l’accès à leurs données et peuvent supprimer complètement un partenaire ou des rôles spécifiques à tout moment.

La fonctionnalité d’accès délégué permet au partenaire de ne pas obtenir d’autres privilèges en dehors du portail de service TRM. Par exemple, si vous invitez un partenaire à gérer les salles du service TRM à l’aide de cette fonctionnalité, aucune autorisation n’est accordée à AAD, au Centre d’administration Teams ou à tout autre produit Microsoft. De plus, les partenaires n’ont pas accès à des salles qui ne sont pas définies dans l’étendue de l’invitation.

Une fois la relation partenaire-client établie (comme décrit dans les « Clients d’intégration » de ce document), le partenaire peut afficher les données de salle dans le service TRM. Ceci inclut toutes les données présentes dans le service TRM, mais dérivées d’autres produits Microsoft. Par exemple, les rapports de qualité des appels dans le portail TRM sont dérivés Teams de qualité des appels.

Les données se trouvent dans le client du client et ne sont pas copiées vers le client du partenaire. 

Le portail MTM utilise AAD’authentification pour valider les informations d’identification du partenaire. Il est important de noter que, pour le moment, les stratégies d’authentification du client ne s’appliquent pas au partenaire. Par exemple, si le client a une stratégie d’authentification multifacteur, elle ne se traduit pas par le partenaire.

Le client peut retirer les journaux d’audit du service TRM, ce qui inclut l’activité des partenaires. Consultez [la journalisation d’audit dans salles Teams service géré.](multi-tenant-auditing.md)

> [!Note]
> AAD audit et l’audit O365 ne capturent pas les journaux à partir du portail TRM.

## <a name="navigating-the-mtm-portal"></a>Navigation dans le portail MTM

Le portail MTM propose deux modèles interactifs pour naviguer entre les données client :

- Les affichages agrégés dans lequel les données de tous vos clients sont consolidées au cours d’une seule liste et peuvent être filtrés.

  > [!Note]
  > Cet affichage est uniquement pris en charge dans la page **Incidents lorsque** l’affichage Activer tous les **tickets** est activé.

  ![Figure 1](../media/multi-tenant-management-partner-001.png)

 - Changement de client lorsque seules les données **du** client sélectionnées dans la liste sont affichées.
