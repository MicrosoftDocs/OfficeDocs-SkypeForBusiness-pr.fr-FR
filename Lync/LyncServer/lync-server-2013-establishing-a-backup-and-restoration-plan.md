---
title: 'Lync Server 2013 : établissement d’un plan de sauvegarde et de restauration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64d9842ccb9d83fb7ce81c326008e36722e45764
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514221"
---
# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a>Établissement d’un plan de sauvegarde et de restauration pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-17_

La création d’un plan de sauvegarde et de restauration nécessite d’effectuer les étapes suivantes :

  - Développement du plan.

  - Implémentation du plan.

  - Maintenance du plan.

<div>

## <a name="developing-a-backup-and-restoration-plan"></a>Développement d’un plan de sauvegarde et de restauration

Une fois que vous avez développé votre stratégie de sauvegarde et de restauration pour Lync Server, utilisez-la pour documenter un plan de sauvegarde et de restauration détaillé. Ce plan doit identifier clairement les priorités et exigences de sauvegarde des données et paramètres. Vous pouvez utiliser les informations contenues dans la [définition d’une stratégie de sauvegarde et de restauration pour Lync server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) et les feuilles de calcul dans les [feuilles de calcul de sauvegarde et de restauration pour Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) afin de faciliter la documentation de votre stratégie. Votre plan doit également contenir des critères identifiant quand et comment restaurer le service.

Lorsque vous développez votre plan, vous devez prendre en compte les éléments suivants :

  - la façon dont vous procéderez à la récupération des serveurs sur le nouveau matériel ;

  - la façon dont vous procéderez à la récupération des services qui requièrent une action de la part de plusieurs unités professionnelles ou départements ;

  - le meilleur moyen d’acquérir rapidement des serveurs de secours ;

  - la durée nécessaire pour effectuer la récupération conformément à votre stratégie. Tenez compte des exigences de votre organisation concernant l’objectif de temps de récupération (RTO).

Modifiez les procédures de sauvegarde et de restauration décrites dans cette rubrique, en ajoutant et en supprimant les procédures appropriées, afin de refléter les serveurs et les composants de votre déploiement. Vous pouvez également ajouter des détails appropriés, tels que la planification de sauvegarde, aux procédures appropriées pour vous assurer que les informations ne sont pas négligées.

<div>


> [!NOTE]  
> Il est recommandé de créer des scripts pour autant d’étapes que possible afin de garantir la qualité et la reproductibilité des procédures.



</div>

Dans votre plan, indiquez qui est responsable de l’examen du plan, qui est responsable du test et de la validation des nouvelles procédures ou outils, et qui doit approuver les modifications apportées au plan et aux procédures connexes.

Pour vous assurer que votre plan de sauvegarde et de restauration répond entièrement à tous les objectifs et priorités établis, obtenez l’approbation des décideurs d’entreprise et des décisionnaires techniques appropriés dans votre organisation avant d’implémenter le plan.

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a>Implémentation du plan de sauvegarde et de restauration

L’implémentation d’un plan de sauvegarde et de restauration nécessite les étapes suivantes :

  - Test et validation du plan.

  - Communication du plan.

  - Validation des opérations de sauvegarde et de restauration.

<div>

## <a name="testing-and-validating-the-plan"></a>Test et validation du plan

Les procédures décrites ici ont été testées et validées dans un environnement de laboratoire. Pour vous assurer que ces procédures ou d’autres procédures fonctionnent dans votre environnement, vous devez tester et valider chaque procédure que vous envisagez d’implémenter. Terminez les tests et la validation avant d’envoyer votre plan pour approbation finale.

</div>

<div>

## <a name="communicating-the-plan"></a>Communication du plan

Votre plan de sauvegarde et de restauration doit identifier clairement qui implémente les procédures et fournir des instructions pas à pas pour l’exécution de ces procédures. Assurez-vous que toutes les personnes responsables de tous les aspects de la sauvegarde et de la restauration comprennent le plan, la façon dont il doit être implémenté, ainsi que son rôle. Cela comprend toutes les exigences d’implémentation pour les éléments suivants :

  - Sauvegarde des pools et des serveurs.

  - Restauration du service.

**Sauvegarde des pools et des serveurs**

Le plan de sauvegarde et de restauration doit contenir toutes les informations requises pour effectuer les procédures de sauvegarde de manière régulière. Les principales informations à communiquer aux membres d’équipe responsables sont les suivantes :

  - Équipe ou personne (spécifiée en tant qu’individu ou rôle) responsable de la sauvegarde de chaque serveur.

  - Planifications spécifiques pour la sauvegarde de chaque serveur.

  - Emplacements de sauvegarde pour chaque type de données (paramètres, base de données et partages de fichiers).

  - Procédures de sauvegarde à utiliser, y compris les outils nécessaires pour effectuer chaque procédure.

  - Informations requises pour effectuer les sauvegardes, comme indiqué dans la [fiche de travail de sauvegarde et de restauration pour Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

  - Méthodes de validation à utiliser pour garantir que les données et les paramètres sont correctement sauvegardés et disponibles pour la restauration, ce qui peut inclure des audits périodiques et des restaurations de test.

**Restauration du service**

Le plan de sauvegarde et de restauration doit inclure toutes les informations nécessaires pour restaurer le service, au cas où un ou plusieurs serveurs subiront une perte de disponibilité du service. Les principales informations à communiquer aux membres d’équipe responsables sont les suivantes :

  - équipe ou personne (identifiée personnellement ou par rôle) chargée de déterminer quand une restauration du service est requise et les procédures à appliquer pour restaurer le service, ainsi que l’équipe ou la personne responsable de l’implémentation des procédures pour chaque scénario de restauration ;

  - critères permettant d’identifier les procédures de restauration les plus appropriées pour une situation spécifique ;

  - Estimations de temps pour la restauration des objectifs de temps de service et de temps de récupération dans chaque scénario de restauration.

  - procédures de restauration à appliquer, y compris les outils nécessaires pour effectuer chaque procédure ;

  - informations requises pour restaurer les données et paramètres. Les feuilles de calcul sont fournies dans les [feuilles de calcul de sauvegarde et de restauration pour Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a>Validation des opérations de sauvegarde et de restauration

Après avoir effectué les tâches de sauvegarde initiales dans votre environnement de production et à intervalles spécifiés (tel qu’indiqué dans votre plan de sauvegarde et de restauration), vérifiez les points suivants :

  - les sauvegardes ont lieu au moment voulu ;

  - Les données et les paramètres sauvegardés sont accessibles.

  - Les procédures de restauration peuvent être effectuées au cours des objectifs de temps de récupération (RTO) spécifiés dans le plan de sauvegarde et de restauration, et les résultats satisfont à tous les besoins de l’entreprise.

  - les fiches de travail de sauvegarde ont été remplies et vérifiées et elles sont stockées à un emplacement sécurisé. Ces feuilles de calcul sont fournies dans les [feuilles de calcul de sauvegarde et de restauration pour Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

  - les procédures de restauration ont été testées et leur fonctionnement a été vérifié, comme indiqué dans votre plan de sauvegarde et de restauration.

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a>Maintenance du plan de sauvegarde et de restauration

Une topologie Lync Server est un environnement dynamique qui est modifié avec votre organisation. Réévaluez votre plan de sauvegarde et de restauration au fur et à mesure que votre organisation change, puis examinez-la régulièrement pour vous assurer qu’elle continue de répondre aux besoins de votre entreprise.

</div>

</div>

<span> </span>

</div>

</div>

</div>

