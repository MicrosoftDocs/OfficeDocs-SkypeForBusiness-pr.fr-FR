---
title: Gestion des partenaires pour les clients
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
description: de gestion des partenaires pour les clients.
f1keywords: ''
ms.openlocfilehash: 84d15f43ff49565dbba915470ea618a69ff74ee8
ms.sourcegitcommit: c8951fe3504c1776d7aec14b79605aaf5d317e7f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2021
ms.locfileid: "61331219"
---
# <a name="partner-management-for-customers"></a>Gestion des partenaires pour les clients


La gestion des partenaires dans salles Teams service géré (TRM) permet aux clients de déléguer sans problème l’accès et les responsabilités à une ou plusieurs organisations partenaires. Les partenaires peuvent uniquement gérer les salles qu’ils sont chargés de gérer. 

## <a name="on-boarding-partners"></a>Partenaires en équipe
   Invitez des partenaires via le portail TRM afin d’établir la relation entre votre organisation et le client de l’organisation partenaire. 

### <a name="invitation-to-partner"></a>Invitation à participer au partenaire

   Dans cette méthode, le partenaire doit fournir les *upns* des utilisateurs qui seront les administrateurs principaux qui vous seront attribués. 

**Pour initier l’invitation** 

1. Connectez-vous au salles Teams géré en tant qu’administrateur MMR.
1. Allez à **Paramètres >** **partenaires partenaires,** puis **sélectionnez Ajouter un partenaire.**
1. Entrez le nom et le nom d’utilisateur principal des administrateurs principaux dans la première ligne.
1. Sélectionnez **Ajouter un contact** à confirmer.
1. Effectuez l’une des opérations suivantes :
   - Pour ajouter un autre utilisateur, répétez l’étape 4.
   - Pour supprimer un utilisateur, sélectionnez l’icône de l’emplacement à droite de l’utilisateur.

    > [!NOTE]
    > Il n’est pas possible d’utiliser des groupes ou des listes de distribution, car l’invitation est liée au nom d’upn.

1. Sélectionnez **Suivant.**
1. Configurez les événements nécessitant une approbation du contrôle des changements. Par défaut, tous les contrôles sont réglés **sur Approbation automatique.**

   > [!NOTE]
   > *Pour l’instant, seule l’approbation automatique est disponible.*
   > 
   >  1.  *Approbation manuelle :* Lorsque le partenaire exécute l’action, une demande d’approbation est générée et le client doit être approuvé. L’action n’est pas implémentée tant que la demande n’a pas été approuvée.
   >  
   >  1. *Approbation automatique :* Lorsque le partenaire exécute l’action, aucune demande d’approbation n’est générée et l’action est implémentée immédiatement.
     
1. Sélectionnez **Suivant.**
1. Affectez les salles que le partenaire gérera, puis sélectionnez **Suivant.**
1. Pour continuer, examinez les conditions et sélectionnez **J’accepte.**
1. Examinez les détails de l’invitation.
1. Sélectionnez **Ajouter un partenaire** pour envoyer l’invitation.

L’invitation est unique pour chaque utilisateur et est indépendante. Le premier utilisateur partenaire qui accepte l’invitation établit le lien entre le partenaire et votre client. Il n’existe aucune association spéciale avec l’utilisateur qui établit le lien, ce qui offre une certaine flexibilité en cas de réassigné. Le rôle Administrateurs primaires sera automatiquement attribué aux utilisateurs suivants à accepter. Le rôle d’administrateur principal doit toujours être au moins un utilisateur.

Pour gérer les utilisateurs dans le rôle d’administrateur principal, voir [Gestion multi-client pour les partenaires.](multi-tenant-management-partner.md)


## <a name="off-boarding-partners"></a>Partenaires de départ

**Pour supprimer un partenaire**

1. Connectez-vous au portail TRM-MTM en tant qu’administrateur MMR.
1. Accédez à **Paramètres > partenaires partenaires.**
1. Sélectionnez le partenaire que vous souhaitez supprimer.
1. Dans le volet Détails du client, sélectionnez **Supprimer le partenaire.**
1. Sélectionnez **Supprimer**. 
1. À l’invite de confirmation pour mettre fin à l’association entre votre client et le client, sélectionnez **Supprimer.**

## <a name="managing-partner-roles"></a>Gestion des rôles de partenaire

Les rôles de partenaire permettent à votre partenaire de déléguer plus granularément les responsabilités au personnel supplémentaire. Le concept de ces rôles est le même que celui décrit dans le contrôle [d’accès en fonction du rôle.](microsoft-teams-rooms-premium-rbac.md) Il est important de noter que les rôles de partenaire sont différents de vos rôles personnalisés. 

Le **rôle d’administrateur** principal est le seul rôle intégré pour chaque partenaire que vous ajoutez. Ce rôle a presque toutes les autorisations pour les salles que vous avez affectées au partenaire pour le service TRM (voir [le tableau 1).](#table-1) Par exemple, si vous avez des salles dans le monde entier et affectez un partenaire pour gérer toutes les salles aux États-Unis, l’administrateur principal serait en mesure de gérer et déléguer les autorisations pour ces salles. Dans ce cas, les administrateurs principaux de ce partenaire n’ont aucune visibilité pour les salles en dehors des États-Unis. 

### <a name="adding-primary-admins-to-partner"></a>Ajout d’administrateurs primaires au partenaire

Si vous avez déjà envoyé une invitation à un partenaire et souhaitez ajouter des utilisateurs à cet administrateur, vous pouvez les ajouter au rôle d’administrateur de partenaire. Une invitation est ainsi envoyée aux utilisateurs ajoutés.

**Pour ajouter de nouveaux utilisateurs à un partenaire existant**

1. Connectez-vous au portail TRM-MTM en tant qu’administrateur MMR.
1. Allez à **Paramètres > rôles.**
1. Sélectionnez  **les rôles de partenaire.** 
1. Sélectionnez **le rôle d’administrateur** principal pour le nom du partenaire correspondant.
1. Dans le volet rôle, sélectionnez **Devoirs.**
1. Sélectionnez **le devoir Administrateurs invités.** 
1. Dans le volet Devoirs des administrateurs invités, sélectionnez **Membres.**
1. Sélectionnez **Modifier.**
1. Entrez le nom d’utilisateur utilisateur du nouvel utilisateur, puis **sélectionnez Ajouter un contact.**
1. Pour confirmer les modifications, sélectionnez **Enregistrer.**

<!--To remove users for an existing partner~~

1. ~~Login to the TRM-MTM portal as a MMR administrator~~
1. ~~Navigate to **Settings > Roles**~~
1. ~~Select the **Partner roles** tab~~
1. ~~Select the **Primary admin** role for the corresponding Partner name~~
1. ~~In the role pane, select the **Assignments** tab~~
1. ~~Select the **Invited admins** assignment~~ 
1. ~~In the Invited admins assignment pane, select the **Members** tab~~
1. ~~Select the **Edit** icon~~
1. ~~Enter the UPN of the new user and select **Add contact**~~
1. ~~Click **Save** to confirm the changes-->




### <a name="table-1"></a>Tableau 1

|Fonctionnalité|Autorisation|**Administrateur MMR**|**Chef de site**|**Site Tech**|**Administrateur de partenaire**|
| :- | :- | :- | :- | :- | :- |
|Salles|Afficher|||||
||Modifier|||||
||Réinitialiser la touche|||||
||Clé de téléchargement|||||
||Désinscrire|||||
|Gestion de groupe|Create |||||
||Afficher|||||
||Modifier|||||
|Mettre à jour la gestion de l’anneau|Create |||||
||Afficher|||||
||Modifier|||||
|Rapports|Afficher|||||
|Gestion des tickets|Créer un incident client|||||
||Afficher|||||
||Mettre à jour|||||
|MmR Paramètres|Afficher|||||
||Modifier|||||
|Gestion de rôle|Afficher |||||
||Modifier|||||





## <a name="security"></a>Sécurité

En tant que client final, vous conservez le contrôle sur l’accès à vos données et pouvez supprimer complètement un partenaire à tout moment. 

La fonctionnalité d’accès délégué permet au partenaire de ne pas obtenir d’autres privilèges en dehors du portail de service TRM. Toutefois, toutes les données présentes dans le service TRM dérivées d’autres produits Microsoft sont considérées comme des données dans le service TRM. Par exemple, bien que les rapports de qualité des appels soient dérivés des Teams de qualité des appels, toutes les données du portail TRM sont dans l’étendue des autorisations. 

Aucune autorisation n’est accordée AAD au Centre Teams’administration microsoft ou à tout autre produit Microsoft. En outre, les partenaires n’ont pas accès à l’affichage ou à la modification de salles non définies dans l’étendue de l’invitation. 

Les données se trouvent dans le client du client et ne sont pas copiées vers le client du partenaire. 

Le portail MTM utilise Azure AD de connexion pour valider les informations d’identification du partenaire. Notez que pour le moment, les stratégies d’authentification du client ne s’appliquent pas au partenaire. Par exemple, si le client a une stratégie d’authentification multifacteur, elle ne se traduit pas par le partenaire. 

Pour consulter des journaux sur l’activité des partenaires, voir [Audit.](multi-tenant-auditing.md) 

> [!NOTE]
> AAD audit et l’audit O365 n’capturent pas les journaux à partir du portail TRM. 
