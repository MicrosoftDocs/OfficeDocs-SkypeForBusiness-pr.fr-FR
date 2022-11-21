---
title: Gestion des partenaires pour les clients
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: altsou
ms.date: 06/09/2022
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
description: gestion des partenaires pour les clients.
f1keywords: ''
ms.openlocfilehash: 56aaf61092dd1bbd61c2734be6da1732f4882e49
ms.sourcegitcommit: baf29d244b428712052553f9e4484e72e727247e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2022
ms.locfileid: "69046863"
---
# <a name="partner-management-for-customers"></a>Gestion des partenaires pour les clients

La gestion des partenaires dans le service de gestion Salles Teams Pro permet aux clients de déléguer en toute transparence l’accès et les responsabilités à une ou plusieurs organisations partenaires. Les partenaires peuvent uniquement gérer les salles qu’ils sont chargés de gérer.

## <a name="on-boarding-partners"></a>Partenaires d’intégration
   Invitez des partenaires via le portail Pro Management pour établir la relation entre votre organisation et le locataire de l’organisation partenaire.
   
> [!NOTE]
> Le partenaire doit satisfaire aux conditions préalables de la [gestion multilocataire pour les partenaires](multi-tenant-management-partner.md).

### <a name="invitation-to-partner"></a>Invitation au partenaire

   Dans cette méthode, vous devez connaître le nom de domaine du partenaire (par exemple, Contoso.com).

**Pour lancer l’invitation** 

1. Connectez-vous au portail de gestion Salles Teams Pro en tant qu’administrateur de service géré.
1. Accédez à **Paramètres >** **Partenaires**, puis sélectionnez **Ajouter un partenaire.**
1. Entrez le nom de domaine dans la première ligne.
1. Configurez le nombre de jours jusqu’à l’expiration de l’invitation en entrant un entier compris entre 1 et 30.
1. Configurez les événements qui nécessiteront une approbation de contrôle des modifications. Par défaut, tous les contrôles sont définis sur **Approbation automatique.**

   > [!NOTE]
   > *Seule l’approbation automatique est actuellement disponible.*
   > 
   >  1.  *Approbation manuelle :* Lorsque le partenaire effectue l’action, une demande d’approbation est générée pour que le client l’examine et l’approuve. L’action n’est pas implémentée tant que la demande n’a pas été approuvée.
   >  
   >  1. *Approbation automatique :* Lorsque le partenaire effectue l’action, aucune demande d’approbation n’est générée et l’action est implémentée immédiatement.
     
1. Sélectionnez **Suivant.**
1. Attribuez les salles que le partenaire gérera, puis sélectionnez **Suivant.**
1. Pour continuer, passez en revue les conditions et sélectionnez **J’accepte.**
1. Passez en revue les détails de l’invitation.
1. Sélectionnez **Ajouter un partenaire** pour envoyer l’invitation.

L’invitation est envoyée aux responsables des locataires dans l’instance de partenaire pour révision. Le premier utilisateur partenaire qui accepte l’invitation établit le lien entre le partenaire et votre locataire et affecte des administrateurs principaux. Il n’existe aucune association spéciale avec l’utilisateur qui établit le lien, ce qui permet une flexibilité si l’utilisateur est réaffecté. Il doit toujours y avoir au moins un utilisateur dans le rôle d’administrateur principal.

Pour gérer les utilisateurs dans le rôle d’administrateur principal, consultez [Gestion multilocataire pour les partenaires](multi-tenant-management-partner.md).

## <a name="off-boarding-partners"></a>Partenaires hors-intégration

**Pour supprimer un partenaire**

1. Connectez-vous au portail Pro Management-Multi-tenant Management (MTM) en tant qu’administrateur de service managé.
1. Accédez à **Paramètres > Partenaires.**
1. Sélectionnez le partenaire que vous souhaitez supprimer.
1. Dans le volet détails du client, sélectionnez **Supprimer le partenaire.**
1. Sélectionnez **Supprimer**. 
1. À l’invite de confirmation pour mettre fin à l’association entre vous et le locataire client, sélectionnez **Supprimer**.

## <a name="managing-partner-roles"></a>Gestion des rôles de partenaires

Les rôles de partenaire permettent à votre partenaire de déléguer plus précisément des responsabilités à un personnel supplémentaire. Le concept de ces rôles est identique à celui décrit dans [Contrôle d’accès en fonction du rôle](rooms-pro-rbac.md). Il est important de noter que les rôles partenaires sont distincts de vos rôles personnalisés. 

Le rôle **Administrateur principal** est le seul rôle intégré pour chaque partenaire que vous ajoutez. Ce rôle dispose de presque toutes les autorisations sur les salles que vous avez attribuées à ce partenaire pour le service TRM (voir [le tableau 1](#table-1)). Par exemple, si vous avez des salles dans le monde entier et que vous affectez un partenaire pour gérer toutes les salles américaines, l’administrateur principal ne peut gérer et déléguer que les autorisations pour ces salles. Dans ce cas, les administrateurs principaux de ce partenaire n’ont aucune visibilité sur les salles en dehors des États-Unis. 

### <a name="adding-primary-admins-to-partner"></a>Ajout d’administrateurs principaux au partenaire

Si vous avez déjà envoyé une invitation à un partenaire et souhaitez déléguer d’autres salles, vous pouvez ajouter des salles au rôle d’administrateur de partenaire.

**Pour ajouter de nouvelles salles à un partenaire existant**

1. Connectez-vous au portail Pro Management-MTM en tant qu’administrateur de service géré.
1. Accédez à **Paramètres > Rôles.**
1. Sélectionnez  **Rôles de partenaire.** 
1. Sélectionnez le rôle **d’administrateur principal** pour le nom de partenaire correspondant.
1. Dans le volet de rôle, sélectionnez **Affectations**.
1. Sélectionnez l’affectation **Administrateurs affectés** .
1. Dans le volet Affectation des administrateurs affectés, sélectionnez **Étendue**.
1. Sélectionnez **Modifier**.
1. Recherchez les salles que vous souhaitez ajouter et sélectionnez la salle souhaitée.
1. Pour confirmer les modifications, sélectionnez **Enregistrer**.

### <a name="table-1"></a>Tableau 1

|Fonctionnalité|Autorisation|**Managed Service Administration**|**Responsable de site**|**Technique du site**|**Administrateur partenaire**|
| :- | :- | :- | :- | :- | :- |
|Chambres|Afficher| &#10004;|&#10004;|&#10004;|&#10004;|
||Modifier|&#10004;|&#10004;|&#10004;|&#10004;|
||Réinitialiser la clé|&#10004;||||
||Télécharger la clé|&#10004;|&#10004;|&#10004;||
||Désinscription|&#10004;|&#10004;|&#10004;||
||Create |&#10004;|&#10004;|||
|Gestion des groupes|Afficher|&#10004;|&#10004;||&#10004;|
||Modifier|&#10004;|&#10004;|||
||Create |&#10004;|&#10004;|||
|Mettre à jour la gestion des anneaux|Afficher|&#10004;|&#10004;||&#10004;|
||Modifier|&#10004;|&#10004;||&#10004;|
|Rapports|Afficher|&#10004;|&#10004;||&#10004;|
||Créer un incident client|&#10004;|&#10004;|&#10004;|&#10004;|
|Gestion des tickets|Afficher|&#10004;|&#10004;|&#10004;|&#10004;|
||Mettre à jour|&#10004;|&#10004;|&#10004;|&#10004;|
|Paramètres de gestion pro|Afficher|&#10004;||||
||Modifier|&#10004;||||
|Gestion des rôles|Afficher |&#10004;|||&#10004;|
||Modifier|&#10004;|||&#10004;|

## <a name="security"></a>Sécurité

En tant que client final, vous conservez le contrôle de l’accès à vos données et pouvez supprimer complètement un partenaire à tout moment. 

Avec la fonctionnalité d’accès délégué, un partenaire n’a pas d’autres privilèges en dehors du portail Pro Management. Toutefois, toutes les données présentes dans le service Pro Management dérivées d’autres produits Microsoft sont considérées comme des données du service. Par exemple, alors que les rapports de qualité des appels sont dérivés des données de qualité des appels Teams, toutes les données du portail Pro Management se trouvent dans l’étendue d’autorisation. 

Aucune autorisation n’est accordée à AAD, au Centre Administration Teams ou à tout autre produit Microsoft. En outre, les partenaires n’ont pas accès à l’affichage ou à la modification des salles non définies dans l’étendue de l’invitation. 

Les données résident dans le locataire du client et ne sont pas copiées vers le locataire du partenaire. 

Le portail MTM utilise l’authentification Azure AD pour valider les informations d’identification de connexion du partenaire. Notez qu’à ce stade, les stratégies d’authentification du client ne s’appliquent pas au partenaire. Par exemple, si le client dispose d’une stratégie d’authentification multifacteur, elle ne se traduit pas par le partenaire. 

Pour extraire les journaux d’activité des partenaires, consultez [Audit](multi-tenant-auditing.md). 

> [!NOTE]
> L’audit AAD et l’audit O365 ne capturent pas les journaux à partir du portail Pro Management. 
