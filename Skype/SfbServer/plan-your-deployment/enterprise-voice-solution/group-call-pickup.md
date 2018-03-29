---
title: Planification de la prise d’appel de groupe dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: Planification pour la collecte d’appeler groupe dans Skype pour Business Server Voix Entreprise, qui permet aux utilisateurs de répondre à des appels au départ destinés à d’autres personnes.
ms.openlocfilehash: ff23b08ca575f7296cbb3706ccdb351b89352804
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-group-call-pickup-in-skype-for-business-2015"></a>Planification de la prise d’appel de groupe dans Skype Entreprise 2015
 
Planification pour la collecte d’appeler groupe dans Skype pour Business Server Voix Entreprise, qui permet aux utilisateurs de répondre à des appels au départ destinés à d’autres personnes.
  
Collecte d’appeler groupe permet aux utilisateurs de répondre aux appels entrants à partir de leurs téléphones à leurs collègues. Cette fonctionnalité accroît la disponibilité de la ligne d’un utilisateur, car elle permet aux autres utilisateurs de répondre à un appel entrant en composant un numéro de groupe de prise d’appel. Lors de la collecte d’appeler groupe est déployé, le nombre d’appels entrants qui sont routées vers la messagerie vocale peut être considérablement réduit, qui est particulièrement utile pour les appels de clients qui sont externes à votre organisation.
  
La fonctionnalité de prise d’appel de groupe est conçue en particulier pour les divisions dans les environnements ouverts. Les appels entrants n’entraînent pas de perturbation, car ils sonnent uniquement sur le poste de leur destinataire. Toutefois, les autres utilisateurs qui entendent la sonnerie peuvent prendre l’appel en composant simplement le numéro de groupe. 
  
Dans les environnements où les utilisateurs ne sont pas situés dans un aménagement de bureau ouvert ou où les utilisateurs partagent une responsabilité commune sont répartis géographiquement, appel d’équipe présente la solution la mieux adaptée. La principale différence entre la collecte d’appeler groupe et appel d’équipe est que, avec collecte d’appel du groupe, un appel entrant sonne uniquement à la destination prévue, mais tous les utilisateurs peuvent toujours choisir de répondre en composant un numéro de groupe. Appel d’équipe, l’appel sonne à tous les téléphones de membres de l’équipe, et tout utilisateur de l’équipe pouvez Décrochez le téléphone pour répondre à l’appel. Une différence supplémentaire entre un groupe appeler remise en mains propres et appel d’équipe est que collecte d’appeler groupe est géré par un administrateur, par le biais de Skype pour Business Server. Avec l’appel de l’équipe, les utilisateurs finaux gérer la fonctionnalité à l’aide de la Skype pour client d’entreprise. Avec un groupe appeler remise en mains propres, par conséquent, cet aspect de la gestion des appels peut être centralisé.
  
Collecte d’appeler groupe repose sur l’application d’appel Park. Lorsque vous déployez le groupe appeler remise en mains propres, vous configurez la table des appels park orbite avec des tranches de numéros d’extension qui sont désignés comme des numéros de groupe collecte d’appel distincts. À l’image des numéros d’appel parqué, les numéros de groupe de prise d’appel doivent être des extensions virtuelles auxquelles n’est affecté aucun utilisateur ou téléphone. Chaque pool frontal où vous déployez collecte d’appeler groupe peut avoir une ou plusieurs plages appel collecte des numéros de groupe. Les plages de numéros de groupe doivent être uniques sur le Skype pour le déploiement du serveur de l’entreprise. 
  
> [!NOTE]
> Les plages de numéros qui sont désignés comme des numéros de prise d’appel de groupe dans la table des appels park orbite ne peut pas être gérés ou affichés à l’aide de la Skype pour le panneau de configuration de Business Server. La seule façon de voir toutes les plages de numéros dans la table des appels park orbite est d’utiliser Skype pour Business Server Management Shell. De même, la seule manière d’ajouter, modifier ou supprimer des numéros de groupe appeler remise en mains propres n’est à utiliser Skype pour Business Server Management Shell. 
  
Après avoir configuré les numéros de groupe de prise d’appel, vous affectez les utilisateurs à un groupe de prise d’appel. Les appels destinés à un utilisateur membre d’un groupe de prise d’appel peuvent être pris par les autres utilisateurs. Lorsqu’un appel parvient à un utilisateur affecté à un groupe de prise d’appel, tout autre utilisateur qui remarque l’appel peut y répondre en composant manuellement le numéro du groupe de prise d’appel. Il n’est pas nécessaire que l’utilisateur qui prend l’appel soit membre du groupe. Lorsqu’un appel est pris par un autre utilisateur, une notification est envoyée au numéro initialement appelé.
  
> [!NOTE]
> Un utilisateur ne peut être membre que d’un seul groupe de prise d’appel. 
  
> [!NOTE]
> Bien que n’importe quel utilisateur dans le Skype pour le déploiement du serveur de l’entreprise peut répondre à un appel à un membre de groupe prise d’appel, la réponse à l’appel de personne doit connaître le numéro de groupe collecte des appels correctes à composer. 
  
Si un utilisateur compose un numéro de groupe de prise d’appel pour répondre à un appel alors que plusieurs téléphones du groupe sonnent, il répond à l’appel qui a sonné en premier.
  
Les paramètres de sonnerie simultanée fonctionnent pour les utilisateurs qui bénéficient de la prise d’appel de groupe. Autrement dit, un appel passé à un utilisateur qui possède le groupe appeler remise en mains propres sonnera pour toutes les destinations des configuration, et un autre utilisateur peut répondre à l’appel. Toutefois, cette règle ne s’applique pas si l’utilisateur configure une sonnerie simultanée pour appeler tous les membres de l’équipe.
  
Prise d’appel de groupe ne permet pas de répondre aux types suivants d’appels :
  
- Appels à destination d’une ligne privée
    
- Appels en provenance d’un contact auquel a été affecté le niveau de confidentialité Famille et amis
    
    > [!TIP]
    > Un utilisateur qui est membre d’un groupe de capture d’appel peut empêcher certains appels d’être récupérés par le biais de collecte d’appeler groupe en marquant le contact sous la forme d’un contact personnel dans le Skype pour client d’entreprise. Pour marquer un contact en tant que contact personnel, définissez le niveau de confidentialité du contact sur Famille et amis. Aucun appel entrant à partir des contacts avec la relation de confidentialité défini à vos amis et famille ne peut pas être récupérée à l’aide de groupe appeler remise en mains propres. 
  
- Partie vidéo d’un appel audio/vidéo 
    
    > [!NOTE]
    > Si un utilisateur répond à un appel audio/vidéo, il reçoit uniquement la partie audio. La personne qui passe l’appel ou celle qui y répond peut doter l’appel de la fonctionnalité vidéo. 
  
- Appels à sonnerie simultanée routés vers les membres d’appel de l’équipe
    
- Appels routés vers un délégué
    
- Appels routés vers un service Response Group
    
Les types d’utilisateurs suivants ne peuvent pas participer à la collecte d’appeler de groupe. C'est-à-dire qu’ils ne doivent pas être inclus dans un groupe de prise d’appel de groupe, et ils ne peut pas récupérer des appels pour les utilisateurs qui disposent de prise d’appel groupe activé.
  
- Utilisateurs hébergés en ligne dans un déploiement hybride
    
- Les utilisateurs qui ne sont pas hébergées sur soit un Skype pour Business Server 2015 pool ou d’un pool Lync Server 2013 mises à jour cumulatives de Lync Server 2013 : février 2013 dans un déploiement sur site
    
Si personne ne répond à un appel destiné à un membre d’un groupe de prise d’appel, l’appel est routé conformément au paramétrage défini dans les paramètres du client. En d’autres termes, l’appel est acheminé vers la messagerie vocale ou transféré à une autre destination.
  
## <a name="deployment-and-requirements"></a>Déploiement et exigences

Collecte d’appeler groupe est déployé automatiquement lors du déploiement de Voix Entreprise et l’application d’appel Park. Activer la collecte d’appeler groupe de configuration de la table d’orbite Park d’appel avec des plages de numéros désignées en tant que numéros de groupe collecte d’appel et séparées puis en affectant des utilisateurs à appeler des groupes de capture et permettant ainsi aux utilisateurs pour la collecte d’appeler groupe.
  
## <a name="clients-supported-for-group-call-pickup"></a>Clients pris en charge pour la collecte d’appeler groupe

Un des clients suivants peuvent servir à répondre aux appels aux membres du groupe appeler remise en mains propres :
  
- Skype Entreprise
    
- Lync 2013
    
- Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Les utilisateurs peuvent utiliser un de ces clients à répondre aux appels aux membres du groupe appeler remise en mains propres, mais les utilisateurs doivent être hébergés sur un Skype pour le pool de serveurs d’entreprise ou d’un pool Lync Server 2013 mises à jour cumulatives de Lync Server 2013 : février 2013. 
  
Les clients et les périphériques suivants ne sont pas pris en charge pour capter les appels aux membres du groupe appeler remise en mains propres :
  
- Lync Mobile
    
- Application Lync pour Windows 8 et Windows RT
    
- Lync pour iPad
    
- Téléphones analogiques
    
- Téléphones avec des numéros RTC
    
## <a name="capacity-planning"></a>Planification de capacité

Le tableau suivant décrit le modèle utilisateur de prise d’appel de groupe que vous pouvez utiliser comme base pour la planification de capacité.
  
> [!IMPORTANT]
> Collecte d’appeler groupe est basé sur l’application d’appel Park. Gardez à l’esprit que, pour la planification de la capacité de récupération de reprise après sinistre, chaque pool d’un pool de paires devrait être en mesure de gérer les charges de travail pour les services appel Park, y compris groupe appeler remise en mains propres, dans les deux pools. 
  
**Modèle de groupe utilisateur prise d’appel**

|**Métrique**|**Par pool frontal <br/> (avec 8 serveurs frontaux)**|**Par serveur Standard Edition server**|
|:-----|:-----|:-----|
|Nombre recommandé d’utilisateurs par groupe  <br/> |50  <br/> |50  <br/> |
|Nombre recommandé de groupes  <br/> |500  <br/> |60  <br/> |
|Nombre maximum d’utilisateurs par pool autorisé pour la prise d’appel de groupe  <br/> |25 000  <br/> |3 000  <br/> |
|Rapport maximal entre le nombre d’appels entrants et le nombre total d’utilisateurs autorisé pour la prise d’appel de groupe par pool et par minute  <br/> |500  <br/> |60  <br/> |
|Taux maximal d’appels récupérés par les utilisateurs avec la prise d’appel de groupe par pool et par minute  <br/> |200  <br/> |25  <br/> |
   
> [!NOTE]
> Pour les pools de Front-End qui ont moins de huit serveurs frontaux, calculer les mesures de façon linéaire. Par exemple, si votre pool frontal est un serveur frontal, vous pouvez calculer la charge maximale au 1/8 des valeurs indiquées dans le tableau. 
  
> [!NOTE]
> Vous pouvez augmenter ou diminuer le nombre d’utilisateurs par groupe et le nombre de groupes recommandés tant que vous ne dépassez pas le nombre d’utilisateurs maximal par pool. Par exemple, votre serveur Standard Edition server peut avoir 120 groupes avec 25 utilisateurs par groupe, car le nombre d’utilisateurs activés pour la collecte d’appeler groupe est toujours dans le maximum de modèle d’utilisateur (c'est-à-dire, les durées de 120 groupes 25 utilisateurs est activées pour la collecte d’appeler groupe de 3 000 utilisateurs). 
  

