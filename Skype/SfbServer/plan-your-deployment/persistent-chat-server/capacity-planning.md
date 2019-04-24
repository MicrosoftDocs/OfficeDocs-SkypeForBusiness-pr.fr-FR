---
title: Planification de la capacité pour le serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur la planification de capacité pour les serveurs de conversation permanente dans Skype pour Business Server 2015.'
ms.openlocfilehash: 08c360b26efd04c34ca1833b0c0022394f8c4ac2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213773"
---
# <a name="capacity-planning-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planification de la capacité pour le serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour en savoir plus sur la planification de capacité pour les serveurs de conversation permanente dans Skype pour Business Server 2015.
  
Persistent Chat Server peuvent effectuer conversation avec plusieurs utilisateur, en temps réel qui peut être permanent pour la recherche et une récupération ultérieure. Contrairement à la messagerie instantanée en groupe (MI) qui a été enregistrée dans la boîte aux lettres d’un utilisateur si l’historique des conversations sont configuré, une session Persistent Chat Server reste ouverte plus longtemps et le contenu est enregistré sur un serveur, ainsi que les messages, les fichiers, les URL et les autres données qui font partie d’un conversation en cours.
  
Planification de la capacité est une part importante de la préparation du déploiement des serveurs de conversation permanente. Cette rubrique fournit des tableaux de planification de la capacité que vous pouvez utiliser pour déterminer la meilleure configuration pour votre déploiement. Il décrit également comment mieux gérer les déploiements de serveur de conversation permanente qui nécessitent une plus grande capacité aux heures de pointe.
  
Avant de lire cette section, familiarisez-vous avec les topologies de conversation permanente. Pour plus d’informations, voir [Plan Persistent Chat Server topology](topology.md).

> [!NOTE] 
> Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. La même fonctionnalité est disponible dans les équipes. Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015. 
  
## <a name="persistent-chat-server-capacity-planning"></a>Planification des capacités de serveur de conversation permanente

Les tableaux suivants peuvent vous aider à la planification de capacité pour le serveur de conversation permanente par modélisation comment différents paramètres de serveur de conversation permanente affectent la capacité.
  
- Planifier la capacité du nombre d’utilisateurs
    
- Planifier la capacité de l’accès aux salles de conversation
    
- Planification de capacité pour l’accès à la salle de conversation par invitation
    
- Planifier la capacité des performances
    
### <a name="plan-capacity-for-number-of-users-for-persistent-chat-server"></a>Planifier la capacité pour nombre d’utilisateurs pour le serveur de conversation permanente

Utilisez l’exemple de tableau suivant pour déterminer le nombre d’utilisateurs que vous serez en mesure de prendre en charge.
  
**Exemple de capacité maximale persistent Chat Server pool**

|||
|:-----|:-----|
|Instances de service de conversation permanente actives  <br/> |4  <br/> |
|Instances de service de conversation permanentes  <br/> |8 (4 instances peuvent être actives au maximum, 4 doivent être inactives.)  <br/> |
|Utilisateurs actifs connectés  <br/> |80,000  <br/> |
|Nombre total d’utilisateurs approvisionnés  <br/> |150,000  <br/> |
|Nombre de points de terminaison  <br/> |120,000  <br/> |
   
Dans l’exemple précédent, le plan est le nombre maximal d’utilisateurs qui Persistent Chat Server permet de prendre en charge : quatre serveurs instances du service de conversation permanente (non attribuable à quatre serveurs plus passives Persistent Chat Server en cours d’exécution pour une haute disponibilité et récupération d’urgence) et 20 000 utilisateurs par serveur, pour un total de 80 000 utilisateurs actifs.
  
### <a name="plan-capacity-for-chat-room-access"></a>Planifier la capacité de l’accès aux salles de conversation

Le tableau suivant peut vous aider à planifier la gestion des accès à la salle de conversation dans un pool de serveurs de conversation permanente.
  
**Exemple de gestion de l’accès aux salles de conversation**

||**Salles de conversation de petite taille**|**Salles de conversation de taille moyenne**|**Salles de conversation de grande taille**|**Total**|
|:-----|:-----|:-----|:-----|:-----|
|Taille des salles de conversation (nombre d’utilisateurs connectés)  <br/> |30 par salle  <br/> |150 par salle  <br/> |16 000 par salle  <br/> ||
|Salles de conversation  <br/> |32,000  <br/> |1,067  <br/> |10  <br/> |33,077  <br/> |
|% de salles auditorium  <br/> |1 %  <br/> |1 %  <br/> |50%  <br/> ||
|% de salles ouvertes  <br/> |3%  <br/> |3%  <br/> |50%  <br/> ||
|Salles ouvertes (aucune appartenance explicite)  <br/> |960  <br/> |32  <br/> |5  <br/> |997  <br/> |
|Salles non ouvertes (salles standard avec appartenance explicite)  <br/> |31,040  <br/> |1.035  <br/> |5  <br/> |32,080  <br/> |
|Salles auditorium (entrée de présentateurs supplémentaires)  <br/> |0  <br/> |32  <br/> |5  <br/> ||
|Salles gérées par appartenance directe  <br/> |50%  <br/> |10%  <br/> |0%  <br/> ||
|Salles gérées par groupes d’utilisateurs  <br/> |50%  <br/> |90%  <br/> |100%  <br/> ||
|Groupes d’utilisateurs dans la liste des membres de chaque salle de conversation pour les salles ouvertes (non spécifiés explicitement)  <br/> |0  <br/> |0  <br/> |0  <br/> ||
|Utilisateurs dans la liste des membres de chaque salle de conversation pour les salles non ouvertes  <br/> |30  <br/> |150  <br/> |16,000  <br/> ||
|Groupes d’utilisateurs dans la liste des membres de chaque salle de conversation pour les salles non ouvertes  <br/> |3  <br/> |5  <br/> |10  <br/> ||
|Utilisateurs et groupes d’utilisateurs dans la liste des gestionnaires de chaque salle de conversation (pour les salles ouvertes et non ouvertes)  <br/> |6  <br/> |6  <br/> |6  <br/> ||
|Utilisateurs et groupes d’utilisateurs dans la liste des présentateurs de chaque salle de conversation auditorium (pour les salles ouvertes et non ouvertes)  <br/> |6  <br/> |6  <br/> |6  <br/> ||
|Entités d’appartenance basées sur l’utilisateur dans toutes les salles non ouvertes  <br/> |465,600  <br/> |15,520  <br/> |-  <br/> ||
|Entités d’appartenance basées sur le groupe d’utilisateurs dans toutes les salles non ouvertes  <br/> |46,560  <br/> |4656  <br/> |50  <br/> ||
|Entités basées sur les utilisateurs et groupes d’utilisateurs dans toutes les salles de conversation auditorium  <br/> |0  <br/> |192  <br/> |50  <br/> ||
|Entités de gestionnaires basées sur les utilisateurs et les groupes d’utilisateurs dans toutes les listes de gestionnaires de salles de conversation  <br/> |192,000  <br/> |6,400  <br/> |60  <br/> ||
|Utilisateurs actifs par salle de conversation  <br/> |30  <br/> |150  <br/> |16,000  <br/> ||
|Salles de conversation par utilisateur  <br/> |12  <br/> |2  <br/> |2  <br/> |16  <br/> |
|Groupes d’utilisateurs dans la liste des membres de chaque salle de conversation  <br/> |10  <br/> |10  <br/> |15  <br/> ||
|Salles gérées par groupes d’utilisateurs  <br/> |50%  <br/> |50%  <br/> |50%  <br/> ||
|Entités d’appartenance basées sur le groupe d’utilisateurs dans toutes les salles de conversation  <br/> |155,200  <br/> |5173  <br/> |68  <br/> ||
|Entités d’appartenance basées sur l’utilisateur dans toutes les salles de conversation  <br/> |465,600  <br/> |77,600  <br/> |72,000  <br/> ||
|Utilisateurs et groupes d’utilisateurs dans chaque liste de gestionnaires, de présentateurs et d’étendue de la salle de conversation  <br/> |6  <br/> |6  <br/> |6  <br/> ||
|Utilisateurs et groupes d’utilisateurs dans toutes les listes de gestionnaires, de présentateurs et d’étendue de salles de conversation  <br/> |192,000  <br/> |6400  <br/> |60  <br/> ||
|Entrées de contrôle d’accès  <br/> |704,160  <br/> |26,768  <br/> |160  <br/> |731,088  <br/> |
|Nombre maximum d’entrées de contrôle d’accès  <br/> ||||2,000,000  <br/> |
   
Dans l’exemple précédent, lorsque vous déployez les serveurs de conversation permanente conformément aux instructions préconisées, ils peuvent gérer jusqu'à 80 000 utilisateurs actifs sur un pool de quatre serveurs avec la conformité activée.
  
Cet exemple indique les catégories des salles de conversation : petite (30 utilisateurs actifs à tout moment), moyenne (150 utilisateurs actifs) et grande (16 000 utilisateurs actifs). Le nombre pris en charge de salles de conversation d’une certaine taille indiqué dans le tableau ci-dessus est calculé en fonction du nombre total :
  
- D’utilisateurs actifs dans le système
    
- D’utilisateurs actifs dans les salles de conversation de la taille donnée
    
- Des salles de conversation de la taille donnée auxquelles se joint un seul utilisateur
    
Pour chaque salle de conversation, le tableau de planification de capacité précédent spécifie le nombre d’entrées de contrôle d’accès associées à la salle de conversation, dont les entrées affectées directement à la salle de conversation. Vous pouvez contrôler l’accès aux salles de conversation individuelles à l’aide des listes de contrôle d’accès. Vous pouvez également contrôler l’accès au niveau de la catégorie. Dans une liste de contrôle d’accès, une entrée de contrôle d’accès individuelle peut être un groupe d’utilisateurs (par exemple, un groupe de sécurité, une liste de distribution ou un utilisateur unique). Vous pouvez définir des entrées de contrôle d’accès pour les gestionnaires, présentateurs et membres de salles de conversation.
  
> [!IMPORTANT]
> En planifiant votre stratégie de gestion des salles de conversation, gardez à l’esprit que le nombre total d’entrées de contrôle d’accès autorisées est de 2 millions. Si le nombre d’entrées de contrôle d’accès calculé dépasse 2 millions, les performances du serveur pourraient se dégrader de manière significative. Pour éviter ce problème, quand cela s’avère possible, assurez-vous que vos entrées de contrôle d’accès sont des groupes d’utilisateurs au lieu d’utilisateurs individuels. 
  
### <a name="plan-capacity-for-managing-chat-room-access-by-invitation"></a>Planifier la capacité pour gérer l’accès aux salles de conversation par invitation

Vous pouvez utiliser le tableau de planification de capacité suivant pour comprendre le nombre d’invitations qui Persistent Chat Server crée et stocke dans la base de données de conversation permanente lorsqu’il est configuré pour envoyer des invitations. Pour gérer des invitations de la catégorie à l’aide de la page **paramètres de catégorie de salle de conversation** dans la Skype pour le panneau de configuration serveur Business ou à l’aide de l’applet de commande Windows PowerShell, **set-csPersistentChatCategory**. Vous pouvez gérer des invitations à une salle de conversation (inséré dans ce qui permet la catégorie) à l’aide de la page **Gestion des salles** lancée à partir de la Skype pour client d’entreprise, ou à l’aide d’une applet de commande Windows PowerShell, **set-csPersistentChatRoom**.
  
Les exemples de données du tableau ci-après supposent que l’option **Invitations** est définie sur **Oui** dans la page **Paramètres de la salle de conversation** pour 50 % de toutes les salles de conversation.
  
> [!IMPORTANT]
> Si la valeur calculée du nombre d’invitations générée par le serveur dépasse 1 million, les performances du serveur pourraient se dégrader de manière significative. Pour éviter ce problème, n’oubliez pas que vous réduisez le nombre de salles de conversation qui sont configurés pour envoyer des invitations ou limiter le nombre d’utilisateurs qui peuvent participer à des salles de conversation qui ont été configurés pour envoyer des invitations. 
  
**Exemple d’accès à la salle de conversation par invitation**

||**Salles de conversation de petite taille**|**Salles de conversation de taille moyenne**|**Salles de conversation de grande taille**|**Total**|
|:-----|:-----|:-----|:-----|:-----|
|Utilisateurs pouvant accéder à la salle de conversation  <br/> |30 par salle  <br/> |150 par salle  <br/> |16 000 par salle  <br/> ||
|Pourcentage de salles qui ont des invitations  <br/> |50%  <br/> |50%  <br/> |50%  <br/> ||
|Salles de conversation configurées pour envoyer des invitations  <br/> |16,000  <br/> |533  <br/> |5  <br/> ||
|Utilisateurs pouvant accéder à la salle de conversation  <br/> |60  <br/> |225  <br/> |16,000  <br/> ||
|Invitations générées par le serveur de conversation permanente  <br/> |960,000  <br/> |120,000  <br/> |80,000  <br/> |1,160,000  <br/> |
|Nombre maximal autorisé d’invitations  <br/> ||||2,000,000  <br/> |
|Modèle 1 - Démarrer avec le nombre attendu de messages par salle par jour  <br/> |||||
|Taux de conversation par salle (par jour)  <br/> |50  <br/> |500  <br/> |100  <br/> |650  <br/> |
|Taux de conversation (par seconde) de toutes les salles  <br/> |55.56  <br/> |18.52  <br/> |0.03  <br/> |74  <br/> |
|Modèle 2 - Démarrer avec le nombre de messages publiés par utilisateur par jour  <br/> |||||
|Taux de conversation par utilisateur par jour  <br/> |15  <br/> |5  <br/> |0.1  <br/> |20  <br/> |
|Taux de conversation par salle (par jour)  <br/> |38  <br/> |375  <br/> |800  <br/> |1,213  <br/> |
|Taux de conversation (par seconde) de toutes les salles  <br/> |41.67  <br/> |13.89  <br/> |0.28  <br/> |56  <br/> |
   
### <a name="plan-capacity-for-persistent-chat-server-performance"></a>Planifier la capacité pour les performances du serveur de conversation permanente

Le tableau suivant décrit le modèle utilisateur pour le serveur de conversation permanente. Il fournit les bases des conditions de planification de la capacité requises et représente une organisation type avec 80 000 utilisateurs simultanés sur quatre serveurs.
  
**Modèle utilisateur des performances persistent Chat Server**

|||
|:-----|:-----|
|Nombre d’utilisateurs actifs connectés  <br/> |80,000  <br/> |
|Nombre d’instances de service de serveur de conversation permanente  <br/> |4  <br/> |
|Taille des petites salles de conversation  <br/> |30 utilisateurs  <br/> |
|Taille des moyennes salles de conversation  <br/> |150 utilisateurs  <br/> |
|Taille des grandes salles de conversation  <br/> |16 000 utilisateurs  <br/> |
|Nombre total de salles de conversation  <br/> |33,077  <br/> |
|Nombre de petites salles de conversation  <br/> |32,000  <br/> |
|Nombre de moyennes salles de conversation  <br/> |1,067  <br/> |
|Nombre de grandes salles de conversation  <br/> |10  <br/> |
|Nombre total de salles de conversation par utilisateur  <br/> |16  <br/> |
|Nombre total de petites salles de conversation par utilisateur  <br/> |12  <br/> |
|Nombre total de moyennes salles de conversation par utilisateur  <br/> |2  <br/> |
|Nombre total de grandes salles de conversation par utilisateur  <br/> |2  <br/> |
|Nombre de salles jointes par utilisateur  <br/> |24  <br/> |
|Taux maximal d’utilisateurs joints  <br/> |10/seconde  <br/> |
|Taux de conversation total  <br/> |24/seconde  <br/> |
|Taux de conversation pour les petites salles de conversation  <br/> |22.22/second  <br/> |
|Taux de conversation pour les moyennes salles de conversation  <br/> |1.67/second  <br/> |
|Taux de conversation pour les grandes salles de conversation  <br/> |~0.15/second  <br/> |
|Pourcentage des salles de conversation configurées pour les invitations  <br/> |50%  <br/> |
|Pourcentage des appartenances directes  <br/> |50%  <br/> |
|Pourcentage des appartenances aux groupes  <br/> |50%  <br/> |
|Nombre moyen d’affiliations anciennes dans les Services de domaine Active Directory  <br/> |100 - 200  <br/> |
|Nombre de contacts abonnés par utilisateur  <br/> |80  <br/> |
|Nombre moyen de points de terminaison par utilisateur  <br/> |1.5  <br/> |
|Nombre moyen de salles de conversation visibles par point de terminaison  <br/> |1.5  <br/> |
|Nombre moyen de salles de conversation visibles par utilisateur  <br/> |2,25 (50 % pour une salle et 50 % pour 2 salles) ; jusqu’à 6 salles ouvertes, une par moniteur  <br/> |
|Nombre de participants interrogés par intervalle  <br/> |25 par salle de conversation visible  <br/> |
|Durée de la fréquence d’interrogation  <br/> |5 minutes  <br/> |
|Nombre de participants interrogés par seconde  <br/> |15,000  <br/> |
|Nombre de changements du statut de présence par heure et par utilisateur  <br/> |6  <br/> |
|Nombre de changements du statut de présence par seconde  <br/> |133.33  <br/> |
   

