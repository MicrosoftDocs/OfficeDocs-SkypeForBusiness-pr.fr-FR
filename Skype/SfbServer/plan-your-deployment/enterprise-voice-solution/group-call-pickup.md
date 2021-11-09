---
title: Planifier la prise d’appel de groupe dans Skype Entreprise
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: Planification de la prise d’appel de groupe Skype Entreprise Server Voix Entreprise, qui permet aux utilisateurs de répondre aux appels destinés à l’origine à d’autres personnes.
ms.openlocfilehash: 94868d78790d9cfaafaf35915c9c3cd1c7a9793f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850697"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a>Planifier la prise d’appel de groupe dans Skype Entreprise
 
Planification de la prise d’appel de groupe Skype Entreprise Server Voix Entreprise, qui permet aux utilisateurs de répondre aux appels destinés à l’origine à d’autres personnes.
  
La prise d’appel de groupe permet aux utilisateurs de répondre aux appels entrants à leurs collègues à partir de leurs propres téléphones. Cela augmente la disponibilité de la ligne d’un utilisateur en permettant à d’autres utilisateurs de répondre à un appel entrant en composant un numéro de groupe de prise d’appel. Lorsque la prise d’appel de groupe est déployée, le nombre d’appels entrants acheminés vers la messagerie vocale peut être considérablement réduit, ce qui est particulièrement utile pour les appels de clients externes à votre organisation.
  
La fonctionnalité de prise d’appel de groupe est conçue en particulier pour les unités d’entreprise dans les environnements de bureau ouverts. Les appels entrants ne perturbent pas car ils sonnent uniquement à la destination prévue. Toutefois, les autres utilisateurs qui entendent la sonnerie peuvent toujours reprendre l’appel en composant simplement le numéro de groupe. 
  
Dans les environnements où les utilisateurs ne sont pas situés dans une disposition de bureau ouverte ou où les utilisateurs qui partagent une responsabilité commune sont répartis géographiquement, l’appel d’équipe présente la solution la plus appropriée. La principale différence entre la prise d’appel de groupe et l’appel d’équipe est que, avec la prise d’appel de groupe, un appel entrant sonne uniquement à la destination prévue, mais tout le monde peut toujours choisir d’y répondre en composant un numéro de groupe. Avec l’appel d’équipe, l’appel sonne sur tous les téléphones des membres de l’équipe, et tous les utilisateurs de l’équipe peuvent prendre le téléphone pour répondre à l’appel. Une autre différence entre la prise d’appel de groupe et l’appel d’équipe est que la prise d’appel de groupe est gérée par un administrateur, Skype Entreprise Server. Avec l’appel d’équipe, les utilisateurs finaux gèrent la fonctionnalité à l’aide Skype Entreprise client. Par conséquent, avec la prise d’appel de groupe, cet aspect de la gestion des appels peut être centralisé.
  
La prise d’appel de groupe repose sur l’application de parcage d’appel. Lorsque vous déployez la prise d’appel de groupe, vous configurez la table des orbites de parcage d’appel avec des plages distinctes de numéros de poste désignés comme numéros de groupe de prise d’appel. Tout comme les numéros de numéros d’appels par parcage, les numéros de groupe de prise d’appel doivent être des extensions virtuelles qui ne sont pas affectées à un utilisateur ou à un téléphone. Chaque pool frontal sur lequel vous déployez la prise d’appel de groupe peut avoir une ou plusieurs plages de numéros de groupe de prise d’appel. Les plages de numéro de groupe doivent être globalement uniques dans Skype Entreprise Server déploiement. 
  
> [!NOTE]
> Les plages de numéros désignées en tant que numéros de prise d’appel de groupe dans la table des numéros d’appels par parcage ne peuvent pas être gérées ou vues à l’aide du Panneau de Skype Entreprise Server de contrôle. La seule façon d’voir toutes les plages de numéro dans la table de numéro d’appel par parcé consiste à utiliser Skype Entreprise Server Management Shell. De même, la seule façon d’ajouter, de modifier ou de supprimer des numéros de prise d’appel de groupe consiste à utiliser Skype Entreprise Server Management Shell. 
  
Après avoir configuré les numéros de groupe de prise d’appel, vous affectez des utilisateurs à un groupe de prise d’appel. Tous les utilisateurs affectés à un groupe de prise d’appel peuvent se voir répondre par d’autres utilisateurs. Lorsqu’un appel arrive à un utilisateur affecté à un groupe de prise d’appel, tout autre utilisateur qui remarque l’appel peut y répondre en composant manuellement le numéro du groupe de prise d’appel. L’utilisateur qui prend l’appel n’a pas besoin d’être membre du groupe. Lorsqu’un appel est pris par un autre utilisateur, une notification est envoyée au numéro appelé à l’origine.
  
> [!NOTE]
> Un utilisateur ne peut être membre que d’un seul groupe de prise d’appel. 
  
> [!NOTE]
> Bien que tout utilisateur du déploiement Skype Entreprise Server puisse répondre à un appel à un membre du groupe de prise d’appel, la personne qui répond à l’appel doit connaître le numéro de groupe de prise d’appel correct à composer. 
  
Si un utilisateur compose un numéro de groupe de prise d’appel pour répondre à un appel lorsque plusieurs téléphones du groupe sonnent, l’utilisateur répond à l’appel qui a sonné le plus longtemps.
  
Les paramètres de sonnerie simultanée fonctionnent pour les utilisateurs qui ont la prise d’appel de groupe. Autrement dit, un appel effectué à un utilisateur qui a la prise d’appel de groupe sonne pour toutes les destinations configurées, et un autre utilisateur peut répondre à l’appel. L’exception à cette règle est lorsque l’utilisateur configure la sonnerie simultanée pour appeler tous les membres de l’équipe.
  
La prise d’appel de groupe ne peut pas être utilisée pour répondre aux types d’appels suivants :
  
- Appels vers une ligne privée
    
- Appels d’un contact qui a été affecté à la relation de confidentialité Amis et famille
    
    > [!TIP]
    > Un utilisateur membre d’un groupe de prise d’appel peut empêcher la récupération de certains appels via la prise d’appel de groupe en marquant le contact comme contact personnel dans le client Skype Entreprise. Pour marquer un contact comme contact personnel, définissez la relation de confidentialité du contact sur Amis et famille. Les appels entrants provenant de contacts dont la relation de confidentialité est définie sur Amis et famille ne peuvent pas être récupérés à l’aide de la prise d’appel de groupe. 
  
- Partie vidéo des appels audio/vidéo 
    
    > [!NOTE]
    > Si un utilisateur répond à un appel audio/vidéo, il ne reçoit que l’audio. La personne qui appelle ou la personne qui répond à l’appel peut faire resserrez l’appel pour ajouter une vidéo. 
  
- Appels de sonnerie simultanée acheminés vers les membres de l’appel d’équipe
    
- Appels acheminés vers un délégué
    
- Appels acheminés vers un groupe Response Group
    
Les types d’utilisateurs suivants ne peuvent pas participer à la prise d’appel de groupe. Autrement dit, ils ne doivent pas être inclus dans un groupe de prise d’appel de groupe et ne peuvent pas prendre d’appels pour les utilisateurs pour qui la prise d’appel de groupe est activée.
  
- Utilisateurs qui sont en ligne dans un déploiement hybride
    
- Utilisateurs qui ne sont pas homed on either a Skype Entreprise Server 2015 pool or a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment
    
Si personne ne répond à un appel à un membre d’un groupe de prise d’appel, l’appel est acheminé comme spécifié dans les paramètres du client. Autrement dit, l’appel est transmis à la messagerie vocale ou est transmis à une autre destination, comme spécifié dans les paramètres du client.
  
## <a name="deployment-and-requirements"></a>Déploiement et conditions requises

La prise d’appel de groupe est déployée automatiquement lorsque vous déployez Voix Entreprise et l’application de parcage d’appel. Vous activez la prise d’appel de groupe en configurant la table des orbites de parcage d’appel avec des plages distinctes de numéros désignés comme numéros de groupe de prise d’appel, puis en attribuant des utilisateurs à des groupes de prise d’appel et en activant les utilisateurs pour la prise d’appel de groupe.
  
## <a name="clients-supported-for-group-call-pickup"></a>Clients pris en charge pour la prise d’appel de groupe

L’un des clients suivants peut être utilisé pour répondre aux appels aux membres de la prise d’appel de groupe :
  
- Skype Entreprise
    
- Lync 2013
    
- Lync 2010
    
- Lync Phone Edition
    
> [!NOTE]
> Les utilisateurs peuvent utiliser l’un de ces clients pour répondre aux appels aux membres de la prise d’appel de groupe, mais ils doivent être regroupés sur un pool Skype Entreprise Server ou un pool Lync Server 2013 avec des mises à jour cumulatives pour Lync Server 2013 : février 2013. 
  
Les clients et périphériques suivants ne sont pas pris en charge pour la prise en charge des appels aux membres de la prise d’appel de groupe :
  
- Lync Mobile
    
- Application Lync pour Windows 8 et Windows RT
    
- Lync pour iPad
    
- Téléphones analogiques
    
- Téléphones avec numéros de réseau téléphonique commuté (PSTN)
    
## <a name="capacity-planning"></a>Planification de la capacité

Le tableau suivant décrit le modèle utilisateur de prise d’appel de groupe que vous pouvez utiliser comme base pour les besoins de planification de la capacité.
  
> [!IMPORTANT]
> La prise d’appel de groupe est basée sur l’application de parcage d’appel. N’oubliez pas que, pour la planification de la capacité de récupération d’urgence, chaque pool d’un pool couplé doit être en mesure de gérer les charges de travail des services de parcage d’appel, y compris la prise d’appel de groupe, dans les deux pools. 
  
**Modèle utilisateur de prise d’appel de groupe**

|**Métrique**|**Par pool frontal  <br/>  (avec 8 serveurs frontux)**|**Par serveur Standard Edition**|
|:-----|:-----|:-----|
|Nombre recommandé d’utilisateurs par groupe  <br/> |50  <br/> |50  <br/> |
|Nombre recommandé de groupes  <br/> |500  <br/> |60  <br/> |
|Nombre maximal d’utilisateurs par pool activés pour la prise d’appel de groupe  <br/> |25 000  <br/> |3,000  <br/> |
|Taux maximal d’appels entrants pour le nombre total d’utilisateurs activés pour la prise d’appel de groupe par pool et par minute  <br/> |500  <br/> |60  <br/> |
|Taux maximal d’appels récupérés par les utilisateurs avec prise d’appel de groupe par pool et par minute  <br/> |200  <br/> |25  <br/> |
   
> [!NOTE]
> Pour les pools frontaux qui ont moins de huit serveurs frontaux, calculez les mesures de manière linéaire. Par exemple, si votre pool frontal possède un serveur frontal, calculez la charge maximale à 1/8 des valeurs indiquées dans le tableau. 
  
> [!NOTE]
> Vous pouvez augmenter ou diminuer le nombre recommandé d’utilisateurs par groupe et le nombre de groupes tant que vous ne dépassez pas le nombre maximal d’utilisateurs par pool. Par exemple, votre serveur Édition Standard peut avoir 120 groupes avec 25 utilisateurs par groupe, car le nombre d’utilisateurs activés pour la prise d’appel de groupe est toujours dans le modèle utilisateur maximal (autrement dit, 120 groupes fois 25 utilisateurs sont 3 000 utilisateurs activés pour la prise d’appel de groupe). 
  

