---
title: Plan de capture d’appel de groupe dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: Planification de la cueillette des appels de groupe dans Skype entreprise Server Voice, qui permet aux utilisateurs de répondre aux appels destinés à des tiers.
ms.openlocfilehash: 0be7adb5b3832851b9c38179416cfedb414508b0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802874"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a>Plan de capture d’appel de groupe dans Skype entreprise
 
Planification de la cueillette des appels de groupe dans Skype entreprise Server Voice, qui permet aux utilisateurs de répondre aux appels destinés à des tiers.
  
La fonction de cueillette des appels de groupe permet aux utilisateurs de répondre aux appels entrants de leurs collègues à partir de leur propre téléphone. Cette fonctionnalité accroît la disponibilité de la ligne d’un utilisateur, car elle permet aux autres utilisateurs de répondre à un appel entrant en composant un numéro de groupe de prise d’appel. Lors du déploiement de la prise d’appel de groupe, le nombre d’appels entrants vers la messagerie vocale peut être considérablement réduit, ce qui est particulièrement utile pour les appels provenant de clients extérieurs à votre organisation.
  
La fonctionnalité de cueillette des appels de groupe est conçue en particulier pour les unités d’entreprise dans les environnements Office ouverts. Les appels entrants n’entraînent pas de perturbation, car ils sonnent uniquement sur le poste de leur destinataire. Toutefois, les autres utilisateurs qui entendent la sonnerie peuvent prendre l’appel en composant simplement le numéro de groupe. 
  
Dans les environnements dans lesquels les utilisateurs ne se trouvent pas dans une mise en page de bureau ouverte ou lorsque les utilisateurs qui partagent une responsabilité commune sont répartis géographiquement, l’équipe appelle la solution la plus adaptée. La principale différence entre un appel de groupe et un appel d’équipe réside dans le fait que, si vous utilisez la fonction d’appel de groupe, un appel entrant sonne uniquement vers la destination prévue, mais tout le monde peut tout de même le répondre en composant un numéro de groupe. Grâce à l’appel d’équipe, l’appel sonne sur le téléphone des membres de l’équipe, et n’importe quel utilisateur de l’équipe peut capter son téléphone pour répondre à l’appel. Il existe une différence supplémentaire entre le prélèvement d’appels de groupe et l’appel d’équipe, car la collecte d’appels de groupe est gérée par un administrateur par le biais de Skype entreprise Server. Dans le cas d’un appel d’équipe, les utilisateurs finaux gèrent la fonctionnalité à l’aide du client Skype entreprise. Ce choix est centralisé grâce à la fonction de redirection des appels de groupe.
  
La cueillette des appels de groupe repose sur l’application de stationnement d’appels. Lorsque vous déployez un appel de groupe, vous configurez la table d’orbite du parc d’appels avec des plages distinctes de numéros d’extension désignés comme numéros de groupe de cueillette d’appel. À l’image des numéros d’appel parqué, les numéros de groupe de prise d’appel doivent être des extensions virtuelles auxquelles n’est affecté aucun utilisateur ou téléphone. Chaque pool frontal sur lequel vous déployez la capture d’appels de groupe peut avoir une ou plusieurs gammes de numéros de groupe de cueillette d’appel. Les plages de numéros de groupe doivent être globalement uniques dans le déploiement de Skype entreprise Server. 
  
> [!NOTE]
> Le panneau de configuration Skype entreprise Server ne peut pas être géré ou affiché dans le panneau de configuration du parc d’appels pour les numéros qui sont désignés en tant que numéros d’appel de groupe. La seule façon d’afficher toutes les plages de chiffres dans la table de parc d’appels est d’utiliser Skype entreprise Server Management Shell. De même, la seule façon d’ajouter, de modifier ou de supprimer des numéros de capture d’appels de groupe consiste à utiliser Skype entreprise Server Management Shell. 
  
Après avoir configuré les numéros de groupe de prise d’appel, vous affectez les utilisateurs à un groupe de prise d’appel. Les appels destinés à un utilisateur membre d’un groupe de prise d’appel peuvent être pris par les autres utilisateurs. Lorsqu’un appel parvient à un utilisateur affecté à un groupe de prise d’appel, tout autre utilisateur qui remarque l’appel peut y répondre en composant manuellement le numéro du groupe de prise d’appel. Il n’est pas nécessaire que l’utilisateur qui prend l’appel soit membre du groupe. Lorsqu’un appel est pris par un autre utilisateur, une notification est envoyée au numéro initialement appelé.
  
> [!NOTE]
> Un utilisateur ne peut être membre que d’un seul groupe de prise d’appel. 
  
> [!NOTE]
> Même si tout utilisateur du déploiement de Skype entreprise Server peut répondre à un appel en tant que membre d’un groupe, la personne qui répond à l’appel doit en savoir le numéro de groupe correspondant au groupe d’appels. 
  
Si un utilisateur compose un numéro de groupe de prise d’appel pour répondre à un appel alors que plusieurs téléphones du groupe sonnent, il répond à l’appel qui a sonné en premier.
  
Les paramètres de sonnerie simultanée fonctionnent pour les utilisateurs qui bénéficient de la prise d’appel de groupe. Autrement dit, un appel passé à un utilisateur disposant d’un appel de groupe sonne pour toutes les destinations configurées et un autre utilisateur peut répondre à l’appel. Toutefois, cette règle ne s’applique pas si l’utilisateur configure une sonnerie simultanée pour appeler tous les membres de l’équipe.
  
La cueillette de groupe ne peut pas être utilisée pour répondre aux types d’appel suivants :
  
- Appels à destination d’une ligne privée
    
- Appels en provenance d’un contact auquel a été affecté le niveau de confidentialité Famille et amis
    
    > [!TIP]
    > Les utilisateurs qui sont membres d’un groupe de captures d’appels peuvent empêcher certains appels d’être récupérés par le biais du prélèvement d’appels de groupe en le marquant en tant que contact personnel dans le client Skype entreprise. Pour marquer un contact en tant que contact personnel, définissez le niveau de confidentialité du contact sur Famille et amis. Tout appel entrant provenant de contacts dont le niveau de confidentialité est défini sur amis et votre famille ne peut pas être récupéré à l’aide de la fonction de cueillette d’appel de groupe. 
  
- Partie vidéo d’un appel audio/vidéo 
    
    > [!NOTE]
    > Si un utilisateur répond à un appel audio/vidéo, il reçoit uniquement la partie audio. La personne qui passe l’appel ou celle qui y répond peut doter l’appel de la fonctionnalité vidéo. 
  
- Appels à sonnerie simultanée routés vers les membres d’appel de l’équipe
    
- Appels routés vers un délégué
    
- Appels routés vers un service Response Group
    
Les types d’utilisateurs suivants ne peuvent pas participer à la cueillette de groupe. Autrement dit, ils ne doivent pas être inclus dans un groupe de prélèvement d’appels de groupe et ne peuvent pas répondre aux appels pour les utilisateurs disposant d’une cueillette de groupe activée.
  
- Utilisateurs hébergés en ligne dans un déploiement hybride
    
- Les utilisateurs qui ne sont pas hébergés sur un pool 2015 de Skype entreprise Server ou un pool 2013 serveur Lync avec des mises à jour cumulatives pour Lync Server 2013:2013 pour le déploiement local
    
Si personne ne répond à un appel destiné à un membre d’un groupe de prise d’appel, l’appel est routé conformément au paramétrage défini dans les paramètres du client. En d’autres termes, l’appel est acheminé vers la messagerie vocale ou transféré à une autre destination.
  
## <a name="deployment-and-requirements"></a>Déploiement et exigences

La prise d’appel de groupe est déployée automatiquement lors du déploiement de l’application voix entreprise et de l’application de parc d’appels. Vous pouvez activer le prélèvement d’appels de groupe en configurant la table orbite du parc d’appels avec des plages de numéros distinctes désignés comme numéros de groupe de capture d’appel, puis en attribuant aux utilisateurs la possibilité d’appeler les groupes de capture et en permettant aux utilisateurs de procéder à un appel de groupe.
  
## <a name="clients-supported-for-group-call-pickup"></a>Clients pris en charge pour le prélèvement d’appels de groupe

L’un des clients suivants peut être utilisé pour répondre aux appels aux membres d’un groupe d’appels de groupe :
  
- Skype Entreprise
    
- Lync 2013
    
- Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Les utilisateurs peuvent utiliser n’importe lequel de ces clients pour répondre aux appels aux membres du groupe, mais les utilisateurs doivent être hébergés sur un pool Skype entreprise Server ou un pool Lync Server 2013 avec des mises à jour cumulatives pour Lync Server 2013:2013 février. 
  
Les clients et appareils suivants ne sont pas pris en charge pour capter les appels vers les membres du groupe d’appels de groupe :
  
- Lync Mobile
    
- Application Lync pour Windows 8 et Windows RT
    
- Lync pour iPad
    
- Téléphones analogiques
    
- Téléphones avec des numéros RTC
    
## <a name="capacity-planning"></a>Planification de capacité

Le tableau suivant décrit le modèle d’utilisateur de capture d’appel de groupe que vous pouvez utiliser comme base pour les exigences de planification de capacité.
  
> [!IMPORTANT]
> Le prélèvement d’appels de groupe est basé sur l’application de parc d’appels. N’oubliez pas que, pour la planification de la capacité de reprise après sinistre, chaque pool d’un pool couplé doit être en mesure de gérer les charges de travail pour les services de parking d’appel, y compris le regroupement des appels de groupe, dans les deux pools. 
  
**Modèle utilisateur de cueillette d’appel de groupe**

|**Mesure**|**Par pool <br/> frontal (avec 8 serveurs frontaux)**|**Par serveur Standard Edition**|
|:-----|:-----|:-----|
|Nombre recommandé d’utilisateurs par groupe  <br/> |50  <br/> |50  <br/> |
|Nombre recommandé de groupes  <br/> |500  <br/> |60  <br/> |
|Nombre maximum d’utilisateurs par pool autorisé pour la prise d’appel de groupe  <br/> |25 000  <br/> |3 000  <br/> |
|Rapport maximal entre le nombre d’appels entrants et le nombre total d’utilisateurs autorisé pour la prise d’appel de groupe par pool et par minute  <br/> |500  <br/> |60  <br/> |
|Taux maximal d’appels récupérés par les utilisateurs avec la prise d’appel de groupe par pool et par minute  <br/> |200  <br/> |1,25  <br/> |
   
> [!NOTE]
> Pour les pools front-end possédant moins de huit serveurs frontaux, calculez les métriques de manière linéaire. Par exemple, si votre pool frontal comporte un serveur frontal, calculez le chargement maximum comme 1/8 de valeurs affichées dans le tableau. 
  
> [!NOTE]
> Vous pouvez augmenter ou diminuer le nombre d’utilisateurs par groupe et le nombre de groupes recommandés tant que vous ne dépassez pas le nombre d’utilisateurs maximal par pool. Par exemple, votre serveur édition standard peut avoir des groupes 120 avec 25 utilisateurs par groupe, car le nombre d’utilisateurs activés pour la capture d’appels de groupe est toujours au maximum au niveau du modèle utilisateur (c’est-à-dire, 120 3 000 groupes). 
  

