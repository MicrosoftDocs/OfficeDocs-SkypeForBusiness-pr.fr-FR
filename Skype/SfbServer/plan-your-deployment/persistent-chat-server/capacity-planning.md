---
title: Planification de la capacité pour le serveur de conversation permanente Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
description: 'Résumé : Consultez cette rubrique pour en savoir plus sur la planification de la capacité du serveur de conversation permanente Skype Entreprise Server 2015.'
ms.openlocfilehash: 48df53528b31babe6419bc42ac303b810abdf197
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389996"
---
# <a name="capacity-planning-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planification de la capacité pour le serveur de conversation permanente Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour en savoir plus sur la planification de la capacité pour le serveur de conversation permanente Skype Entreprise Server 2015.
  
Le serveur de conversation permanente peut effectuer une conversation en temps réel multi-utilisateur qui peut persister pour une récupération et une recherche ultérieures. Contrairement à la messagerie instantanée de groupe enregistrée dans la boîte aux lettres d’un utilisateur si l’historique des conversations est configuré, une session de serveur de conversation permanente reste ouverte plus longtemps et le contenu est enregistré sur un serveur, ainsi que les messages, fichiers, URL et autres données faisant partie d’une conversation en cours.
  
La planification de la capacité est un élément important de la préparation du déploiement du serveur de conversation permanente. Cette rubrique fournit des tableaux de planification de la capacité que vous pouvez utiliser pour déterminer la meilleure configuration pour votre déploiement. Il explique également comment gérer au mieux les déploiements de serveurs de conversation permanente qui nécessitent une plus grande capacité aux heures de pointe.
  
Avant de lire cette section, vous devez connaître les topologies de conversation permanente. Pour plus d’informations, voir [Plan Persistent Chat Server topology](topology.md).

> [!NOTE] 
> La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015. 
  
## <a name="persistent-chat-server-capacity-planning"></a>Planification de la capacité du serveur de conversation permanente

Les tableaux suivants peuvent vous aider à planifier la capacité du serveur de conversation permanente en modélisant l’impact de différents paramètres du serveur de conversation permanente sur la capacité.
  
- Planifier la capacité du nombre d’utilisateurs
    
- Planifier la capacité pour l’accès aux salles de conversation
    
- Planifier la capacité pour l’accès aux salles de conversation par invitation
    
- Planifier la capacité pour les performances
    
### <a name="plan-capacity-for-number-of-users-for-persistent-chat-server"></a>Planifier la capacité du nombre d’utilisateurs pour le serveur de conversation permanente

Utilisez l’exemple de tableau suivant pour déterminer le nombre d’utilisateurs que vous serez en mesure de prendre en charge.
  
**Exemple de capacité maximale du pool de serveurs de conversation permanente**

- Instances de service de conversation permanente active : 4  <br/> 
- Instances de service de conversation permanente : 8 (4 au maximum peuvent être actifs ; 4 doivent être inactifs)  <br/>
- Utilisateurs actifs connectés : 80 000  <br/>
- Nombre total d’utilisateurs provisionés : 150 000  <br/>
- Nombre de points de terminaison : 120 000  <br/>
   
Dans l’exemple précédent, l’objectif est de prendre en charge le nombre maximal d’utilisateurs que le serveur de conversation permanente autorise : quatre serveurs/instances du service de conversation permanente (peut avoir quatre serveurs passifs supplémentaires exécutant le serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence) et 20 000 utilisateurs par serveur, pour un total de 80 000 utilisateurs actifs.
  
### <a name="plan-capacity-for-chat-room-access"></a>Planifier la capacité pour l’accès aux salles de conversation

L’exemple de tableau suivant peut vous aider à planifier la gestion de l’accès aux salles de conversation dans un pool de serveurs de conversation permanente.
  
**Exemple de gestion de l’accès aux salles de conversation**

|&nbsp;|Petites salles de conversation|Moyennes salles de conversation|Grandes salles de conversation|Total|
|:-----|:-----|:-----|:-----|:-----|
|Taille des salles de conversation (nombre d’utilisateurs connectés)   |30 par salle   |150 par salle   |16 000 par salle   ||
|Salles de conversation   |32,000   |1,067   |10   |33,077   |
|% de salles qui sont des auditoriums   |1 %   |1 %   |50%   ||
|% de salles ouvertes   |3 %   |3 %   |50%   ||
|Ouvrir des salles (aucune appartenance explicite)   |960   |32   |5   |997   |
|Salles non ouvertes (salles normales avec appartenance explicite)   |31,040   |1.035   |5   |32,080   |
|Salles auditorium (entrée de présentateurs supplémentaire)   |0   |32   |5   ||
|Salles gérées par appartenance directe   |50%   |10 %   |0%   ||
|Salles gérées par groupes d’utilisateurs   |50%   |90 %   |100 %   ||
|Groupes d’utilisateurs dans la liste d’appartenance de chaque salle de conversation pour les salles ouvertes (non spécifié explicitement)   |0   |0   |0   ||
|Utilisateurs dans la liste des membres de chaque salle de conversation pour les salles non ouvertes   |30   |150   |16,000   ||
|Groupes d’utilisateurs dans la liste d’appartenance de chaque salle de conversation pour les salles non ouvertes   |3   |5   |10   ||
|Utilisateurs et groupes d’utilisateurs dans la liste des responsables de chaque salle de conversation (pour les salles ouvertes et non ouvertes)   |6    |6    |6    ||
|Utilisateurs et groupes d’utilisateurs dans la liste des présentateurs de chaque salle de conversation auditorium (pour les salles ouvertes et non ouvertes)   |6    |6    |6    ||
|Entités d’appartenance basées sur l’utilisateur dans toutes les salles non ouvertes   |465,600   |15,520   |-   ||
|Entités d’appartenance basées sur un groupe d’utilisateurs dans toutes les salles non ouvertes   |46,560   |4656   |50   ||
|Entités basées sur les utilisateurs et les groupes d’utilisateurs dans toutes les salles de conversation auditorium   |0   |192   |50   ||
|Entités de gestionnaire basées sur les utilisateurs et les groupes d’utilisateurs dans toutes les listes de responsables de salles de conversation   |192,000   |6,400   |60   ||
|Utilisateurs actifs par salle de conversation   |30   |150   |16,000   ||
|Salles de conversation par utilisateur   |12    |2   |2   |16   |
|Groupes d’utilisateurs dans la liste des membres de chaque salle de conversation   |10   |10   |15    ||
|Salles gérées par groupes d’utilisateurs   |50%   |50%   |50%   ||
|Entités d’appartenance basées sur le groupe d’utilisateurs dans toutes les salles de conversation   |155,200   |5173   |68   ||
|Entités d’appartenance basées sur l’utilisateur dans toutes les salles de conversation   |465,600   |77,600   |72,000   ||
|Utilisateurs et groupes d’utilisateurs dans chaque liste de gestionnaires, de présentateurs et d’étendue de la salle de conversation   |6    |6    |6    ||
|Utilisateurs et groupes d’utilisateurs dans toutes les listes de gestionnaire, de présentateur et d’étendue des salles de conversation   |192,000   |6400   |60   ||
|Entrées de contrôle d’accès   |704,160   |26,768   |160   |731,088   |
|Nombre maximum d’entrées de contrôle d’accès   ||||2,000,000   |
   
Dans l’exemple précédent, lorsque vous déployez les serveurs de conversation permanente conformément aux recommandations, ils peuvent gérer jusqu’à 80 000 utilisateurs actifs dans un pool de quatre serveurs avec la conformité activée.
  
Cet exemple montre les salles de conversation classées comme petites (30 utilisateurs actifs à tout moment), moyennes (150 utilisateurs actifs) et grandes (16 000 utilisateurs actifs). Le nombre pris en charge de salles de conversation d’une certaine taille dans le tableau ci-dessus est calculé en fonction du nombre total de :
  
- D’utilisateurs actifs dans le système
    
- D’utilisateurs actifs dans les salles de conversation de la taille donnée
    
- Des salles de conversation de la taille donnée auxquelles se joint un seul utilisateur
    
Pour chaque salle de conversation, le tableau de planification de capacité précédent spécifie le nombre d’entrées de contrôle d’accès associées à la salle de conversation, y compris les entrées qui sont affectées directement à la salle de conversation. Vous pouvez contrôler l’accès aux salles de conversation individuelles à l’aide des listes de contrôle d’accès. Vous pouvez également contrôler l’accès au niveau de la catégorie. Dans une liste de contrôle d’accès, une entrée de contrôle d’accès individuelle peut être soit un groupe d’utilisateurs, par exemple un groupe de sécurité, une liste de distribution, soit un utilisateur unique. Vous pouvez définir des entrées de contrôle d’accès pour les gestionnaires, présentateurs et membres de salles de conversation.
  
> [!IMPORTANT]
> Dans la planification de votre stratégie de gestion des salles de conversation, n’oubliez pas que le nombre total d’entrées de contrôle d’accès autorisées est de 2 millions. Si les entrées de contrôle d’accès calculées dépassent 2 millions, les performances du serveur pourraient se dégrader considérablement. Pour éviter ce problème, dans la mesure du possible, assurez-vous que vos entrées de contrôle d’accès sont des groupes d’utilisateurs plutôt que des utilisateurs individuels. 
  
### <a name="plan-capacity-for-managing-chat-room-access-by-invitation"></a>Planifier la capacité de gestion de l’accès aux salles de conversation par invitation

Vous pouvez utiliser le tableau de planification de capacité suivant pour comprendre le nombre d’invitations que le serveur de conversation permanente crée et stocke dans la base de données de conversation permanente lorsqu’il est configuré pour envoyer des invitations. Vous gérez les invitations sur la catégorie à l’aide de la page **Paramètres** de catégorie de salle de conversation dans le Panneau de configuration Skype Entreprise Server ou à l’aide de l’Windows PowerShell cmdlet **set-csPersistentChatCategory**. Vous pouvez gérer les invitations sur une salle de conversation (en fonction de ce que la catégorie autorise) à l’aide de **la page Gestion** de salle lancée à partir du client Skype Entreprise ou à l’aide d’une cmdlet Windows PowerShell, **set-csPersistentChatRoom**.
  
Les exemples de données du tableau suivant supposent que, dans la page **Paramètres** de la salle de conversation pour 50 % de toutes les **salles** de conversation, l’option Invitations est définie sur **Oui**.
  
> [!IMPORTANT]
> Si la valeur calculée du nombre d’invitations générées par le serveur dépasse 1 million, les performances du serveur pourraient se dégrader de manière significative. Pour éviter ce problème, assurez-vous de réduire le nombre de salles de conversation configurées pour envoyer des invitations ou de limiter le nombre d’utilisateurs qui peuvent rejoindre des salles de conversation configurées pour envoyer des invitations. 
  
**Exemple d’accès à la salle de conversation par invitation**

|&nbsp;|Petites salles de conversation|Moyennes salles de conversation|Grandes salles de conversation|Total|
|:-----|:-----|:-----|:-----|:-----|
|Utilisateurs qui peuvent accéder à la salle de conversation   |30 par salle   |150 par salle   |16 000 par salle   ||
|Pourcentage de salles qui ont des invitations   |50%   |50%   |50%   ||
|Salles de conversation configurées pour envoyer des invitations   |16,000   |533   |5   ||
|Utilisateurs pouvant accéder à la salle de conversation   |60   |225   |16,000   ||
|Invitations générées par le serveur de conversation permanente   |960,000   |120,000   |80,000   |1,160,000   |
|Nombre maximal autorisé d’invitations   ||||2,000,000   |
|Modèle 1 : démarrer avec le nombre attendu de messages par salle et par jour   |||||
|Taux de conversation par salle (par jour)   |50   |500   |100   |650   |
|Taux de conversation (par seconde) dans toutes les salles   |55.56   |18.52   |0.03   |74   |
|Modèle 2 : démarrer avec le nombre de messages publiés par utilisateur et par jour   |||||
|Taux de conversation par utilisateur et par jour   |15    |5   |0,1   |20   |
|Taux de conversation par salle (par jour)   |38   |375   |800   |1,213   |
|Taux de conversation (par seconde) dans toutes les salles   |41.67   |13.89   |0.28   |56   |
   
### <a name="plan-capacity-for-persistent-chat-server-performance"></a>Planifier la capacité des performances du serveur de conversation permanente

Le tableau suivant décrit le modèle utilisateur pour le serveur de conversation permanente. Il fournit la base des exigences de planification de capacité et représente une organisation classique avec 80 000 utilisateurs simultanés sur quatre serveurs.
  
**Modèle utilisateur des performances du serveur de conversation permanente**

- Nombre d’utilisateurs actifs connectés : 80 000  <br/>
- Nombre d’instances de service de serveur de conversation permanente : 4  <br/>
- Taille des petites salles de conversation : 30 utilisateurs  <br/> 
- Taille des moyennes salles de conversation : 150 utilisateurs  <br/>
- Taille des grandes salles de conversation : 16 000 utilisateurs  <br/>
- Nombre total de salles de conversation : 33 077  <br/> 
- Nombre de petites salles de conversation : 32 000  <br/> 
- Nombre de moyennes salles de conversation : 1 067  <br/> 
- Nombre de grandes salles de conversation : 10  <br/> 
- Nombre total de salles de conversation par utilisateur : 16  <br/> 
- Nombre de petites salles de conversation par utilisateur : 12  <br/> 
- Nombre de moyennes salles de conversation par utilisateur : 2  <br/> 
- Nombre de grandes salles de conversation par utilisateur : 2  <br/> 
- Nombre de salles jointes par utilisateur : 24  <br/>
- Taux de participation maximale : 10/seconde  <br/> 
- Taux total de conversation : 24/seconde  <br/> 
- Taux de conversation pour les petites salles de conversation : 22,22/seconde  <br/> 
- Taux de conversation pour les moyennes salles de conversation : 1,67/seconde  <br/> 
- Taux de conversation pour les grandes salles de conversation : ~0,15/seconde  <br/> 
- Pourcentage de salles de conversation configurées pour les invitations : 50 %  <br/>
- Pourcentage d’appartenances directes : 50 %  <br/>
- Pourcentage d’appartenances à un groupe : 50 %  <br/> 
- Nombre moyen d’affiliations ancêtres dans les services de domaine Active Directory : 100 - 200  <br/>
- Nombre de contacts abonnés par utilisateur : 80  <br/> 
- Nombre moyen de points de terminaison par utilisateur : 1,5  <br/> 
- Nombre moyen de salles de conversation visibles par point de terminaison : 1,5  <br/> 
- Nombre moyen de salles de conversation visibles par utilisateur : 2,25 (50 % pour 1 salle et 50 % pour 2 salles) ; Jusqu’à 6 salles ouvertes, une par moniteur  <br/> 
- Nombre de participants interrogés par intervalle : 25 par salle de conversation visible  <br/> 
- Durée de l’intervalle d’interrogation : 5 minutes  <br/> 
- Nombre de participants interrogés par seconde : 15 000  <br/>
- Nombre de modifications de présence par heure et par utilisateur : 6  <br/> 
- Nombre de modifications de présence par seconde : 133,33  
   

