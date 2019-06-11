---
title: 'Lync Server 2013: établissement d’un plan de sauvegarde et de restauration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b3516e63a7cbada4a89fad3540406e38b299fef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a>Établissement d’un plan de sauvegarde et de restauration pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-17_

Pour créer un plan de sauvegarde et de restauration, procédez comme suit:

  - Développement du plan.

  - Implémentation du plan.

  - Maintenance du plan.

<div>

## <a name="developing-a-backup-and-restoration-plan"></a>Développement d’un plan de sauvegarde et de restauration

Après avoir développé votre stratégie de sauvegarde et de restauration pour Lync Server, utilisez-la pour documenter une planification de sauvegarde et de restauration détaillées. Votre plan doit indiquer clairement les priorités et les exigences en matière de sauvegarde des données et des paramètres. Pour plus d’informations sur la [création d’une stratégie de sauvegarde et de restauration de lync 2013 server](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) 2013, vous pouvez utiliser les informations contenues dans la création d’une stratégie de sauvegarde et de restauration pour [Lync Server](lync-server-2013-backup-and-restoration-worksheets.md) et faciliter la documentation de votre stratégie. Votre plan doit également contenir des critères de décision concernant le mode de restauration du service.

Lorsque vous développez votre plan, vous devez prendre en compte les éléments suivants:

  - Le mode de récupération des serveurs sur le nouveau matériel.

  - Le mode de récupération des services nécessitant une action de la part de plusieurs domaines ou services commerciaux.

  - Comment vous pouvez obtenir des serveurs de réserve rapidement.

  - Le temps nécessaire à la récupération en utilisant votre stratégie. Prenez en compte les exigences de votre organisation concernant les objectifs de temps de récupération.

Modifiez les procédures de sauvegarde et de restauration décrites dans cette rubrique, en ajoutant et en supprimant les procédures le cas échéant, afin de répercuter les serveurs et les composants dans votre déploiement. Vous pouvez également ajouter des détails appropriés, comme le planning de sauvegarde, aux procédures appropriées pour vous assurer que les informations ne sont pas ignorées.

<div>


> [!NOTE]  
> Il est recommandé de créer des scripts pour autant de étapes que possible afin de garantir la qualité et la reproductibilité des procédures.



</div>

Dans votre plan, spécifiez qui est responsable de la consultation du plan, qui est chargé de tester et de valider tout nouveau mode ou outil, et qui doit approuver les modifications apportées au plan et aux procédures associées.

Pour vous assurer que votre plan de sauvegarde et de restauration répond bien à toutes les priorités et buts définis, obtenez l’approbation des décideurs et des décisions techniques appropriés de votre organisation avant d’implémenter le plan.

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a>Implémentation du plan de sauvegarde et de restauration

Pour implémenter un plan de sauvegarde et de restauration, procédez comme suit:

  - Test et validation du plan.

  - Communication du plan.

  - Valider les opérations de sauvegarde et de restauration.

<div>

## <a name="testing-and-validating-the-plan"></a>Test et validation du plan

Les procédures décrites dans cet article ont été testées et validées dans un environnement Lab. Pour vous assurer que les procédures suivantes s’appliquent à votre environnement, testez et validez les procédures que vous envisagez d’implémenter. Finalisez le test et la validation avant de remettre votre plan pour approbation finale.

</div>

<div>

## <a name="communicating-the-plan"></a>Communication du plan

Votre plan de sauvegarde et de restauration doit clairement décrire les personnes qui mettent en œuvre des procédures et des instructions détaillées pour la réalisation des procédures. Assurez-vous que toutes les personnes responsables de la sauvegarde et de la restauration comprennent le plan, la manière dont il doit être implémenté et son rôle. Cela inclut toutes les exigences en matière d’implémentation pour les éléments suivants:

  - Sauvegarde du pool et du serveur.

  - Restauration du service.

**Sauvegarde du serveur et du pool**

Le plan de sauvegarde et de restauration doit inclure toutes les informations nécessaires à l’achèvement régulier des procédures de sauvegarde. Les principales informations à communiquer aux membres de l’équipe responsable incluent les éléments suivants:

  - Équipe ou personne (spécifiée en tant qu’individu ou rôle) responsable de la sauvegarde de chaque serveur.

  - Plannings spécifiques de sauvegarde de chaque serveur.

  - Emplacements de sauvegarde pour chaque type de données (paramètres, base de données et partages de fichiers).

  - Procédures de sauvegarde à utiliser, y compris les outils nécessaires à la réalisation de chaque procédure.

  - Les informations nécessaires à la réalisation des sauvegardes, telles qu’elles sont décrites dans les [feuilles de calcul de sauvegarde et de restauration pour Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

  - Les méthodes de validation à utiliser pour garantir que les données et paramètres soient correctement sauvegardés et disponibles à des fins de restauration, qui peuvent inclure des audits périodiques et des restaurations de tests.

**Restauration du service**

Le plan de sauvegarde et de restauration doit inclure toutes les informations nécessaires à la restauration du service, en cas de perte de l’un ou de plusieurs serveurs pour lesquels le service n’est pas disponible. Les principales informations à communiquer aux membres de l’équipe responsable incluent les éléments suivants:

  - Une équipe ou une personne (spécifiée en tant qu’individu ou rôle) qui est responsable de la détermination du moment où la restauration du service est requise et des procédures à utiliser pour restaurer le service ainsi que de l’équipe ou de la personne responsable de la mise en œuvre de procédures pour chacun d’eux. scénario de restauration.

  - Critères permettant de déterminer quelles procédures de restauration conviennent le mieux pour une situation spécifique.

  - Temps d’estimation pour la restauration de l’objectif de temps de service et de temps de reprise (RTO) dans chaque scénario de restauration.

  - Procédures de restauration à utiliser, y compris les outils nécessaires à la réalisation de chaque procédure.

  - Informations nécessaires à la restauration des données et des paramètres. Les feuilles de calcul sont fournies dans les [feuilles de calcul et de restauration pour Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a>Valider les opérations de sauvegarde et de restauration

Après avoir effectué les efforts de sauvegarde initiale dans votre environnement de production et à des intervalles spécifiques (comme décrit dans votre plan de sauvegarde et de restauration), vous devez vérifier les points suivants:

  - Les sauvegardes se produisent selon les besoins.

  - Les données et paramètres sauvegardés sont accessibles.

  - Les procédures de restauration peuvent être exécutées dans les temps d’objectif de temps de restauration spécifiés dans le plan de sauvegarde et de restauration, et les résultats répondent à toutes les exigences métiers.

  - Les feuilles de calcul de sauvegarde sont achevées et vérifiées, et sont stockées dans un emplacement sécurisé. Ces feuilles de calcul sont fournies dans les [feuilles de calcul et de restauration pour Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

  - Les procédures de restauration ont été testées et vérifiées pour fonctionner comme prévu, comme indiqué dans votre plan de sauvegarde et de restauration.

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a>Maintenance du plan de sauvegarde et de restauration

Une topologie de serveur Lync est un environnement dynamique modifié par votre organisation. Réévaluez votre plan de sauvegarde et de restauration au fur et à mesure de l’évolution de votre organisation et examinez-le régulièrement pour vous assurer qu’il continue de répondre aux besoins de votre entreprise.

</div>

</div>

<span> </span>

</div>

</div>

</div>

