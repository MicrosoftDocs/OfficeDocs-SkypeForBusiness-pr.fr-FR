---
title: Planification de groupe ou d’appel dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: Planification de groupe d’appel collecte dans Skype pour Business Server Enterprise Voice, qui permet aux utilisateurs répondre aux appels originellement prévues pour d’autres personnes.
ms.openlocfilehash: b62a6fae7f2e7e145332db242eb8793692205adf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924233"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a>Planification de groupe ou d’appel dans Skype entreprise
 
Planification de groupe d’appel collecte dans Skype pour Business Server Enterprise Voice, qui permet aux utilisateurs répondre aux appels originellement prévues pour d’autres personnes.
  
Collecte d’appel de groupe permet aux utilisateurs de répondre aux appels entrants avec leurs collègues à partir de leurs téléphones. Cette fonctionnalité accroît la disponibilité de la ligne d’un utilisateur, car elle permet aux autres utilisateurs de répondre à un appel entrant en composant un numéro de groupe de prise d’appel. Lors de la collecte d’appel de groupe est déployé, le nombre d’appels entrants qui sont routés vers la messagerie vocale permettre être réduit, ce qui est particulièrement utile pour les appels de clients qui sont externes à votre organisation.
  
La fonctionnalité de groupe d’appel collecte est conçue en particulier pour les divisions dans des environnements open office. Les appels entrants n’entraînent pas de perturbation, car ils sonnent uniquement sur le poste de leur destinataire. Toutefois, les autres utilisateurs qui entendent la sonnerie peuvent prendre l’appel en composant simplement le numéro de groupe. 
  
Dans les environnements où les utilisateurs se trouvent pas dans une présentation office open ou où les utilisateurs qui partagent la responsabilité commune sont répartis géographiquement, appel d’équipe présente la solution la plus adaptée. La principale différence entre le groupe d’appel collecte et appel d’équipe est que, avec le groupe d’appel collecte, un appel entrant sonne uniquement à la destination prévue, mais tout le monde peut toujours choisir d’y répondre en composant un numéro de groupe. Appel d’équipe, l’appel sonne à tous les téléphones de membres de l’équipe, et tous les utilisateurs de l’équipe peuvent Décrochez le téléphone pour répondre à l’appel. Une différence supplémentaire entre un groupe d’appel collecte et appel d’équipe est que collecte d’appel de groupe est géré par un administrateur, par le biais de Skype pour Business Server. Avec l’appel d’équipe, les utilisateurs finaux gérer la fonctionnalité à l’aide de la Skype pour client d’entreprise. Avec un groupe d’appel collecte, par conséquent, cet aspect de la gestion des appels peut être centralisé.
  
Groupe d’appel collecte repose sur l’application de parcage d’appel. Lorsque vous déployez la collecte d’appel de groupe, vous configurez la table d’orbite de parcage d’appel avec des plages de numéros de poste qui sont désignés comme numéros d’appel groupe pickup séparées. À l’image des numéros d’appel parqué, les numéros de groupe de prise d’appel doivent être des extensions virtuelles auxquelles n’est affecté aucun utilisateur ou téléphone. Chaque pool frontal où vous déployez le groupe d’appel collecte peut avoir une ou plusieurs plages appel collecte des numéros de groupe. Les plages de numéros de groupe doivent être globalement uniques dans le Skype pour le déploiement de serveur d’entreprise. 
  
> [!NOTE]
> Plages de numéros qui sont désignés en tant que groupe d’appel collecte numéros dans la table d’orbite de parcage d’appel ne peut pas être gérés ou affichés à l’aide de la Skype pour le panneau de configuration serveur Business. La seule façon de voir toutes les plages de numéros dans la table d’orbite de parcage d’appel consiste à utiliser Skype pour Business Server Management Shell. De même, la seule façon d’ajouter, modifier ou supprimer des numéros de groupe d’appel collecte consiste à utiliser Skype pour Business Server Management Shell. 
  
Après avoir configuré les numéros de groupe de prise d’appel, vous affectez les utilisateurs à un groupe de prise d’appel. Les appels destinés à un utilisateur membre d’un groupe de prise d’appel peuvent être pris par les autres utilisateurs. Lorsqu’un appel parvient à un utilisateur affecté à un groupe de prise d’appel, tout autre utilisateur qui remarque l’appel peut y répondre en composant manuellement le numéro du groupe de prise d’appel. Il n’est pas nécessaire que l’utilisateur qui prend l’appel soit membre du groupe. Lorsqu’un appel est pris par un autre utilisateur, une notification est envoyée au numéro initialement appelé.
  
> [!NOTE]
> Un utilisateur ne peut être membre que d’un seul groupe de prise d’appel. 
  
> [!NOTE]
> Bien que n’importe quel utilisateur dans le Skype pour le déploiement de serveur d’entreprise peut répondre à un appel à un membre du groupe pickup appel, la réponse à l’appel de personne doit connaître le numéro de groupe pickup appel correct à composer. 
  
Si un utilisateur compose un numéro de groupe de prise d’appel pour répondre à un appel alors que plusieurs téléphones du groupe sonnent, il répond à l’appel qui a sonné en premier.
  
Les paramètres de sonnerie simultanée fonctionnent pour les utilisateurs qui bénéficient de la prise d’appel de groupe. Autrement dit, un appel fait un utilisateur ayant le groupe d’appel collecte sonnera pour toutes les destinations configurées et un autre utilisateur peut répondre à l’appel. Toutefois, cette règle ne s’applique pas si l’utilisateur configure une sonnerie simultanée pour appeler tous les membres de l’équipe.
  
Collecte d’appel de groupe ne peut être utilisé pour répondre aux types d’appels suivants :
  
- Appels à destination d’une ligne privée
    
- Appels en provenance d’un contact auquel a été affecté le niveau de confidentialité Famille et amis
    
    > [!TIP]
    > Un utilisateur qui est un membre d’un groupe d’appel pickup peut empêcher certains appels d’être récupérés par le biais de groupe d’appel collecte en marquant le contact comme un contact personnel dans le Skype pour client d’entreprise. Pour marquer un contact en tant que contact personnel, définissez le niveau de confidentialité du contact sur Famille et amis. Un appel entrant à partir des contacts avec le niveau de confidentialité est défini sur amis et famille ne peut pas être récupéré à l’aide du groupe d’appel collecte. 
  
- Partie vidéo d’un appel audio/vidéo 
    
    > [!NOTE]
    > Si un utilisateur répond à un appel audio/vidéo, il reçoit uniquement la partie audio. La personne qui passe l’appel ou celle qui y répond peut doter l’appel de la fonctionnalité vidéo. 
  
- Appels à sonnerie simultanée routés vers les membres d’appel de l’équipe
    
- Appels routés vers un délégué
    
- Appels routés vers un service Response Group
    
Les types d’utilisateurs suivants ne peuvent pas participer à la collecte d’appel de groupe. Autrement dit, ils ne doivent pas figurer dans un groupe de collecte d’appel de groupe et ne peut pas récupérer les appels pour les utilisateurs qui ont le groupe d’appel collecte est activé.
  
- Utilisateurs hébergés en ligne dans un déploiement hybride
    
- Les utilisateurs qui ne sont pas hébergés sur un soit Skype pour Business Server 2015 pool ou un pool Lync Server 2013 avec les mises à jour cumulatives pour Lync Server 2013 : dans un déploiement local de février 2013
    
Si personne ne répond à un appel destiné à un membre d’un groupe de prise d’appel, l’appel est routé conformément au paramétrage défini dans les paramètres du client. En d’autres termes, l’appel est acheminé vers la messagerie vocale ou transféré à une autre destination.
  
## <a name="deployment-and-requirements"></a>Déploiement et exigences

Groupe d’appel collecte est déployé automatiquement lors du déploiement d’Enterprise Voice et l’application de parcage d’appel. Activer la collecte d’appel de groupe Configuration de la table d’orbites de parcage d’appel avec des plages de numéros désignés comme numéros d’appel groupe collecte et séparées puis en attribuant aux utilisateurs d’appeler des groupes de collecte et de l’activation des utilisateurs pour la collecte d’appel de groupe.
  
## <a name="clients-supported-for-group-call-pickup"></a>Clients pris en charge pour la collecte d’appel de groupe

Un des clients suivants peut être utilisé pour répondre aux appels aux membres du groupe d’appel collecte :
  
- Skype Entreprise
    
- Lync 2013
    
- Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Les utilisateurs peuvent utiliser une de ces clients pour répondre aux appels aux membres du groupe d’appel collecte, mais les utilisateurs doivent être hébergés sur un Skype pour le pool de serveurs d’entreprise ou d’un pool Lync Server 2013 avec les mises à jour cumulatives pour Lync Server 2013 : février 2013. 
  
Les clients et périphériques suivants ne sont pas pris en charge pour prendre les appels aux membres du groupe d’appel collecte :
  
- Lync Mobile
    
- Application Lync pour Windows 8 et Windows RT
    
- Lync pour iPad
    
- Téléphones analogiques
    
- Téléphones avec des numéros RTC
    
## <a name="capacity-planning"></a>Planification de capacité

Le tableau suivant décrit le modèle utilisateur collecte d’appel de groupe que vous pouvez utiliser comme base pour les exigences de planification de capacité.
  
> [!IMPORTANT]
> Groupe d’appel collecte est basé sur l’application de parcage d’appel. N’oubliez pas que, pour la planification de capacité récupération d’urgence, chaque pool d’un pool associé doit être en mesure de gérer les charges de travail pour les services de parcage d’appel, y compris prise d’appel de groupe, dans les deux pools. 
  
**Modèle utilisateur collecte de groupe d’appel**

|**Mesure**|**Par pool frontal <br/> (avec 8 serveurs frontaux)**|**Par serveur Standard Edition**|
|:-----|:-----|:-----|
|Nombre recommandé d’utilisateurs par groupe  <br/> |50  <br/> |50  <br/> |
|Nombre recommandé de groupes  <br/> |500  <br/> |60  <br/> |
|Nombre maximum d’utilisateurs par pool autorisé pour la prise d’appel de groupe  <br/> |25 000  <br/> |3 000  <br/> |
|Rapport maximal entre le nombre d’appels entrants et le nombre total d’utilisateurs autorisé pour la prise d’appel de groupe par pool et par minute  <br/> |500  <br/> |60  <br/> |
|Taux maximal d’appels récupérés par les utilisateurs avec la prise d’appel de groupe par pool et par minute  <br/> |200  <br/> |25  <br/> |
   
> [!NOTE]
> Pour les pools frontaux ayant moins de huit serveurs frontaux, calculer les mesures de façon linéaire. Par exemple, si votre pool frontal a un serveur frontal, calculer la charge maximale en tant que les valeurs indiquées dans le tableau 1/8. 
  
> [!NOTE]
> Vous pouvez augmenter ou diminuer le nombre d’utilisateurs par groupe et le nombre de groupes recommandés tant que vous ne dépassez pas le nombre d’utilisateurs maximal par pool. Par exemple, votre serveur Standard Edition server peut avoir 120 groupes avec 25 utilisateurs par groupe, car le nombre d’utilisateurs activés pour la collecte d’appel de groupe est toujours dans le maximum de modèle d’utilisateur (autrement dit, les durées de 120 groupes 25 utilisateurs est activés pour le groupe d’appel collecte de 3 000 utilisateurs). 
  

