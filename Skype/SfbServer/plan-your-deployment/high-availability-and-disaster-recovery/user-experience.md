---
title: Expérience utilisateur défaillance d’un pool dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
description: Découvrez ce que les utilisateurs rencontrent lorsqu’un pool frontal bascule ou Business Server échoue pendant la récupération d’urgence dans Skype.
ms.openlocfilehash: de272ec6bc45a005a56c3e16385f7bcc292c8a1a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903046"
---
# <a name="user-experience-during-pool-failure-in-skype-for-business-server"></a>Expérience utilisateur défaillance d’un pool dans Skype pour Business Server
 
Découvrez ce que les utilisateurs rencontrent lorsqu’un pool frontal bascule ou Business Server échoue pendant la récupération d’urgence dans Skype.
  
Si un pool est basculé, tous les utilisateurs du pool affecté sont obligés de se déconnecter, puis de se reconnecter au pool de sauvegarde. Pendant quelques instants, les utilisateurs qui se connectent au pool de sauvegarde peuvent être en mode Résistance. En mode résilience, les utilisateurs ne peuvent pas effectuer des tâches entraînerait une modification permanente sur Skype pour Business Server, tels que l’ajout d’un contact. Une fois le basculement terminé, tous les utilisateurs peuvent obtenir tous les services du pool de sauvegarde.
  
Tous les appels, réunions ou conversations en cours d’un utilisateur au moment de la défaillance du pool sont interrompus, et l’utilisateur doit rétablir ces sessions après le basculement pour continuer.
  
Les utilisateurs ne sont pas rapatriés pendant le basculement ou la restauration automatique. Les utilisateurs hébergés sur un pool qui subit une défaillance sont temporairement pris en charge par le pool de sauvegarde. Lorsque le pool d’accueil est restauré, l’administrateur peut restaurer ces utilisateurs afin qu’ils soient pris en charge par leur pool d’accueil d’origine.
  
Notez que la base de données du serveur de localisation (LIS, Location Information Server) n’est pas répliquée sur le pool de sauvegarde. Il est recommandé que l’administrateur sauvegarde régulièrement la base de données LIS et utilise la dernière copie de sauvegarde pour la restaurer dans le pool de sauvegarde après le basculement.
  
## <a name="user-experience-during-failover"></a>Expérience utilisateur durant le basculement

Lorsqu’un utilisateur se trouve dans un pool subissant une défaillance, il est déconnecté. Toute session d’égal à égal à laquelle l’utilisateur participait est terminée, de même que les conférences organisées par cet utilisateur. L’utilisateur ne peut se reconnecter qu’après l’expiration du minuteur de résistance du serveur d’inscriptions avancé ou lorsque l’administrateur lance des procédures de basculement. Lorsque l’utilisateur se reconnecte, il se connecte au pool de sauvegarde. S’il se connecte avant que le basculement soit terminé, il sera en mode Résistance jusqu’à la fin du basculement. C’est seulement alors que l’utilisateur peut établir de nouvelles sessions pour rétablir des sessions précédentes.
  
## <a name="user-experience-during-failback"></a>Expérience utilisateur durant la restauration

La restauration automatique du pool peut survenir pendant qu’un utilisateur affecté est connecté au pool de sauvegarde ; l’utilisateur reste connecté et opérationnel pendant la restauration. Notez que l’exécution du processus de restauration automatique prend plusieurs minutes. À titre de référence, il devrait prendre jusqu’à 60 minutes pour un pool de 20 000 utilisateurs.
  
Les tableaux suivants présentent des détails supplémentaires sur la façon dont un utilisateur avec un client est affecté pendant et après la restauration automatique, ainsi que la façon dont les utilisateurs d’autres pools voient un utilisateur d’un pool en cours de restauration et interagissent avec lui. 
  
Le terme utilisateur affecté fait référence à tous les utilisateurs qui ont été basculés à partir du pool d’accueil et qui sont pris en charge par le pool de sauvegarde. Tout utilisateur initialement hébergé sur le pool de sauvegarde n’est pas un utilisateur affecté.
  
**Expérience utilisateur pour un utilisateur affecté dans un pool en restauration automatique**

|**Statut de l’utilisateur ou tâche**|**Durant la restauration automatique**|**Une fois la restauration automatique terminée**|
|:-----|:-----|:-----|
|Statut d’un utilisateur déjà connecté  <br/> |L’utilisateur reste connecté au pool de sauvegarde. À un certain moment, l’utilisateur sera déconnecté et reconnecté au pool d’accueil d’origine, en mode Résistance.  <br/> |L’utilisateur reste connecté et passe en mode normal.  <br/> |
|Connexion d’un nouvel utilisateur  <br/> |L’utilisateur peut se connecter au pool d’accueil en mode Résistance.  <br/> |L’utilisateur peut se connecter au pool d’accueil d’origine en mode normal.  <br/> |
|Conférences en cours organisées par un utilisateur affecté  <br/> |Toutes les modalités de conférence sont terminées. Le bouton Rejoindre s’affiche, mais aucun utilisateur ne peut rejoindre la conférence tant que l’utilisateur affecté est en mode Résistance.  <br/> |Toutes les modalités fonctionnent à présent. Chaque participant doit cliquer pour participer à la conférence.  <br/> |
|Conférences en cours organisées par un utilisateur non affecté  <br/> |La conférence se poursuit et l’utilisateur affecté peut rester dans la conférence. L’utilisateur affecté est limité à ce qu’il peut faire en mode Résistance.  <br/> |La conférence se poursuit. L’utilisateur affecté peut rester dans la conférence et toutes les modalités fonctionnent une fois que l’utilisateur a quitté le mode Résistance.  <br/> |
|Planification ou modification de réunions planifiées, création de conférences ad hoc  <br/> |Impossibles pendant que l’utilisateur est en mode Résistance.  <br/> |Disponibles pour toutes les modalités.  <br/> |
|Présence telle qu’elle est vue par les autres utilisateurs du même pool  <br/> |Présence inconnue pendant que l’utilisateur est connecté au pool de sauvegarde en mode Résistance.  <br/> |Affiche le dernier état de présence défini par l’utilisateur, et les changements du statut de présence sont maintenant reflétés.  <br/> |
|Disponibilité de la liste de contacts et du Service de carnet d’adresses  <br/> |Non disponibles  <br/> |Disponibles  <br/> |
|Ensemble des sessions et modalités pair à pair  <br/> |Disponibles  <br/> |Disponibles  <br/> |
   
**Expérience utilisateur pour un utilisateur hébergé dans un pool non affecté lors de la restauration automatique d’un autre pool**

|**Tâche utilisateur**|**Durant la restauration automatique**|**Une fois la restauration automatique terminée**|
|:-----|:-----|:-----|
|Affichage de la présence de l’utilisateur affecté  <br/> |Affiche le dernier état de présence défini par l’utilisateur.  <br/> |Opérationnel. Les utilisateurs non affectés voient les mises à jour effectuées par les utilisateurs affectés.  <br/> |
|Conférences en cours organisées par un utilisateur affecté  <br/> |Toutes les modalités de conférence sont terminées.  <br/> |Toutes les modalités fonctionnent à présent. Chaque participant doit cliquer pour participer à la conférence.  <br/> |
|Conférences en cours organisées par un utilisateur non affecté  <br/> |La conférence se poursuit. L’utilisateur affecté peut rester dans la conférence et toutes les modalités fonctionnent.  <br/> |La conférence se poursuit. L’utilisateur affecté peut rester dans la conférence et toutes les modalités fonctionnent.  <br/> |
|Ensemble des sessions et modalités pair à pair  <br/> |Disponibles  <br/> |Disponibles  <br/> |
   

