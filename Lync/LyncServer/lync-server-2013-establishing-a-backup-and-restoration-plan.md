---
title: Établissement d’un plan de sauvegarde et de restauration
TOCTitle: Établissement d’un plan de sauvegarde et de restauration
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh202183(v=OCS.15)
ms:contentKeyID: 53095474
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Établissement d’un plan de sauvegarde et de restauration

 

_**Dernière rubrique modifiée :** 2013-02-17_

La création d’un plan de sauvegarde et de restauration nécessite d’effectuer les étapes suivantes :

  - développement du plan ;

  - implémentation du plan ;

  - tenue à jour du plan.

## Développement d’un plan de sauvegarde et de restauration

Après avoir développé votre stratégie de sauvegarde et de restauration pour Lync Server, utilisez-la afin de documenter un plan de sauvegarde et de restauration détaillé. Ce plan doit identifier clairement les priorités et exigences de sauvegarde des données et paramètres. Vous pouvez utiliser les informations fournies dans la rubrique [Établissement d’une stratégie de sauvegarde et de restauration](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) et les fiches de travail fournies dans l’[Feuilles de travail de sauvegarde et de restauration](lync-server-2013-backup-and-restoration-worksheets.md) pour faciliter la documentation de votre stratégie. Votre plan doit également contenir des critères identifiant quand et comment restaurer le service.

Lors du développement du plan, il convient de prendre en compte les aspects suivants :

  - la façon dont vous procéderez à la récupération des serveurs sur le nouveau matériel ;

  - la façon dont vous procéderez à la récupération des services qui requièrent une action de la part de plusieurs unités professionnelles ou départements ;

  - le meilleur moyen d’acquérir rapidement des serveurs de secours ;

  - la durée nécessaire pour effectuer la récupération conformément à votre stratégie. Prenez en compte les exigences de votre organisation en matière d’objectif de durée de récupération.

Modifiez les procédures de sauvegarde et de restauration fournies dans ce document, en ajoutant ou supprimant des procédures en fonction des serveurs et composants de votre déploiement. Vous pouvez également ajouter des détails spécifiques, tels que la planification de sauvegarde, aux procédures appropriées afin de vous assurer de n’oublier aucune information.

> [!NOTE]  
> Il est recommandé de créer des scripts pour le plus grand nombre d’étapes possibles, afin de garantir la qualité et la reproductibilité des procédures.

Dans votre plan, identifiez la personne responsable de la vérification du plan, celle responsable des tests et de la validation de tout nouvel outil ou procédure, ainsi que celle devant approuver les modifications apportées au plan et procédures associées.

Pour vous assurer que votre plan de sauvegarde et de restauration répond entièrement à tous les objectifs et priorités établis, obtenez l’approbation des décisionnaires techniques et commerciaux au sein de votre organisation avant de mettre en œuvre le plan.

## Implémentation du plan de sauvegarde et de restauration

L’implémentation d’un plan de sauvegarde et de restauration nécessite d’effectuer les étapes suivantes :

  - test et validation du plan ;

  - communication du plan ;

  - validation des opérations de sauvegarde et de restauration.

## Test et validation du plan

Les procédures décrites dans ce document ont été testées et validées dans un environnement de laboratoire. Pour vous assurer du fonctionnement de toute procédure que vous prévoyez d’implémenter dans votre environnement, il convient de la tester et de la valider. Procédez aux tests et à la validation avant de soumettre votre plan pour approbation finale.

## Communication du plan

Votre plan de sauvegarde et de restauration doit identifier clairement qui implémente les procédures et fournir des instructions pas à pas pour l’exécution de ces procédures. Il convient de s’assurer que toute personne responsable d’un aspect de la sauvegarde ou de la restauration comprend le plan, la façon dont il est mis en œuvre et en quoi consiste son rôle. Cela comprend toutes les exigences d’implémentation pour les éléments suivants :

  - sauvegarde des pools et des serveurs ;

  - restauration du service.

**Sauvegarde des pools et des serveurs**

Le plan de sauvegarde et de restauration doit contenir toutes les informations requises pour effectuer les procédures de sauvegarde de manière régulière. Les principales informations à communiquer aux membres d’équipe responsables sont les suivantes :

  - équipe ou personne (identifiée personnellement ou par rôle) responsable de la sauvegarde de chaque serveur ;

  - calendriers spécifiques de sauvegarde de chaque serveur ;

  - emplacements de sauvegarde pour chaque type de données (paramètres, base de données et partages de fichiers) .

  - procédures de sauvegarde à appliquer, y compris les outils nécessaires pour effectuer chaque procédure ;

  - informations requises pour effectuer les sauvegardes, comme indiqué dans l’[Feuilles de travail de sauvegarde et de restauration](lync-server-2013-backup-and-restoration-worksheets.md) ;

  - méthodes de validation à appliquer pour s’assurer que les données et paramètres sont sauvegardés correctement et disponibles pour la restauration, ce qui peut inclure des audits périodiques et des tests de restauration.

**Restauration du service**

Le plan de sauvegarde et de restauration doit contenir toutes les informations nécessaires à la restauration du service, pour le cas où un ou plusieurs serveurs subiraient une perte provoquant l’indisponibilité du service. Les principales informations à communiquer aux membres d’équipe responsables sont les suivantes :

  - équipe ou personne (identifiée personnellement ou par rôle) chargée de déterminer quand une restauration du service est requise et les procédures à appliquer pour restaurer le service, ainsi que l’équipe ou la personne responsable de l’implémentation des procédures pour chaque scénario de restauration ;

  - critères permettant d’identifier les procédures de restauration les plus appropriées pour une situation spécifique ;

  - estimations du temps nécessaire à la restauration du service dans chaque scénario de restauration ;

  - procédures de restauration à appliquer, y compris les outils nécessaires pour effectuer chaque procédure ;

  - informations requises pour restaurer les données et paramètres. Des fiches de travail sont disponibles dans l’[Feuilles de travail de sauvegarde et de restauration](lync-server-2013-backup-and-restoration-worksheets.md).

## Validation des opérations de sauvegarde et de restauration

Après avoir effectué les tâches de sauvegarde initiales dans votre environnement de production et à intervalles spécifiés (tel qu’indiqué dans votre plan de sauvegarde et de restauration), vérifiez les points suivants :

  - les sauvegardes ont lieu au moment voulu ;

  - les données et paramètres sauvegardés sont accessibles ;

  - les procédures de restauration peuvent être appliquées dans les délais spécifiés dans le plan de sauvegarde et de restauration et les résultats répondent à toutes les exigences professionnelles stipulées dans votre plan de sauvegarde et de restauration ;

  - les fiches de travail de sauvegarde ont été remplies et vérifiées et elles sont stockées à un emplacement sécurisé. Ces fiches de travail sont disponibles dans l’[Feuilles de travail de sauvegarde et de restauration](lync-server-2013-backup-and-restoration-worksheets.md)

  - les procédures de restauration ont été testées et leur fonctionnement a été vérifié, comme indiqué dans votre plan de sauvegarde et de restauration.

## Maintenance du plan de sauvegarde et de restauration

Une topologie Lync Server est un environnement dynamique qui change à mesure que votre organisation évolue. Réévaluez votre plan de sauvegarde et de restauration au fil de cette évolution et étudiez-le régulièrement afin de vous assurer qu’il continue de répondre aux besoins de votre organisation.

