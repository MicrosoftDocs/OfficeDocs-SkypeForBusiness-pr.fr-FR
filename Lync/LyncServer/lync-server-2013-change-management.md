---
title: 'Lync Server 2013 : gestion des modifications'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change management
ms:assetid: 73c774f5-c12f-4c72-be73-e07dc745b994
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720336(v=OCS.15)
ms:contentKeyID: 63969618
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7de514dee1b9e185e880660be656b493ae520340
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-management-in-lync-server-2013"></a>Gestion des modifications dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-08-18_

Les modifications apportées à l’environnement informatique sont inévitables. Les modifications incluent les nouvelles technologies, les systèmes, les applications, le matériel, les outils, les processus et les modifications apportées aux rôles et aux responsabilités. Un système de gestion des modifications efficace vous permet d’apporter des modifications à l’environnement informatique rapidement et avec une interruption de service minimale. Un système de gestion des modifications permet de réunir les équipes impliquées dans la modification d’un système. Par exemple, choisir de tirer parti des Office Web Apps. Il s’agit d’une application de service Lync intégrée qui permet aux utilisateurs de lire et de modifier des documents dans un navigateur. Une fois que vous êtes en production, l’implémentation de ce service nécessite l’implication de plusieurs équipes :

  - **Équipe de test**   cette équipe a pour but de tester la charge Office Web Apps sur un serveur de test, dans le processus fournissant des informations sur les modèles d’utilisation attendus et les performances attendues des serveurs de production.

  - **Administrateurs Lync cette**   équipe détermine la stratégie de déploiement et les scripts de l’installation où elle était possible. L’équipe est chargée de s’assurer que la modification est déployée sur l’environnement de production et qu’elle est responsable de l’administration. L’équipe doit comprendre l’impact des modifications et les intégrer aux procédures avant la mise en production des modifications.

  - **Équipe réseau cette**   équipe est responsable des modifications apportées aux règles de pare-feu autorisant l’accès à partir d’Internet aux serveurs de pools internes de Lync. L’équipe est également chargée de collaborer avec les administrateurs Lync pour s’assurer que la bande passante disponible peut prendre en charge la charge supplémentaire.

  - **Équipe de sécurité**   cette équipe évalue la sécurité et minimise les risques. L’équipe de sécurité doit examiner les vulnérabilités connues et s’assurer que les risques de sécurité sont minimisés.

  - **Équipe d’acceptation des utilisateurs**   cette équipe est composée d’utilisateurs qui souhaitent tester le système et proposer des commentaires pour les améliorations.

Le processus de gestion des modifications définit les responsabilités de chaque équipe et planifie le travail à effectuer, en intégrant des vérifications et des tests là où ils sont nécessaires. Les contrôles de modification varient en fonction de la complexité et de l’effet attendu d’une modification. Elles peuvent varier de l’approbation automatique des modifications mineures à la modification des réunions de révision, en révisions complètes au niveau du projet. Pour expliquer ce mieux, les groupes de modifications sont présentés dans cette section.

  - **Modifications majeures les**   modifications majeures ont un effet global sur le système et peuvent nécessiter une intervention de différentes équipes. Voici un exemple de mise à niveau vers Lync Server 2013. Les modifications majeures concernent de nombreuses équipes et peut-être différents systèmes. Le processus de gestion des modifications inclut probablement une ou plusieurs réunions de révision des modifications pour informer les équipes qui seront impliquées dans la modification ou être concernées par la modification.

  - **Modifications importantes les**   modifications importantes nécessitent des ressources importantes pour la planification, la création et l’implémentation. Des contrôles de modification appropriés doivent être introduits pour garantir que l’effet de la modification est compris, que les procédures de déploiement sont testées et que les plans de restauration et d’urgence sont prêts. Un exemple de modification importante concerne le déploiement d’une nouvelle mise à jour cumulative.

  - **Modifications mineures**   les modifications mineures n’ont pas une incidence significative sur l’environnement informatique, par exemple, la modification de certaines stratégies Lync via le panneau de configuration Microsoft Lync Server 2013.

  - **Modifications standard les**   modifications standard sont effectuées régulièrement et sont bien comprises et documentées. Le processus de gestion des modifications doit examiner toutes les modifications apportées aux procédures. Elle ne doit pas être nécessaire pour les modifications de routine, telles que la création d’une base de données de contenu ou l’ajout d’un utilisateur.

L’exemple suivant de gestion des modifications examine le mode d’interaction entre différentes équipes et les actions effectuées lors du déploiement d’un nouveau Service Pack. Ces actions sont organisées et gérées par le processus de gestion des modifications.

  - **Émettre une demande**   de modification l’équipe de sécurité a évalué le Service Pack le plus récent et a confirmé qu’il résout une vulnérabilité possible dans le système de production. L’équipe déclenche une demande de modification pour que la nouvelle mise à jour cumulative s’applique à tous les serveurs qui exécutent Lync Server.

  - **Notes de publication du Service Pack consultez**   les notes de publication du Service Pack pour identifier l’impact sur le système.

  - **Une série de tests de laboratoire est effectuée**   l’équipe de l’administrateur Lync doit effectuer des mises à jour de test sur un serveur dans un environnement de test pour déterminer si le Service Pack peut être appliqué sans affecter les applications et systèmes serveur installés. S’il existe des applications tierces ou créées en interne qui s’interfacent avec Lync Server dans un environnement de production, elles doivent également être testées. Ces tests peuvent également être utilisés pour estimer le temps nécessaire pour effectuer les mises à niveau.

  - **Les utilisateurs sont informés de la panne**   que l’équipe de l’administrateur Lync, l’équipe de communication ou le support technique de l’utilisateur informe tous les utilisateurs concernés du cycle de maintenance planifié et de la durée pendant laquelle le service n’est pas disponible.

  - **Une sauvegarde complète de Lync est effectuée avant la mise à niveau**   l’équipe de l’administrateur Lync doit vérifier qu’il existe une sauvegarde valide pouvant être utilisée pour rétablir l’état du système d’origine en cas d’échec de l’installation du Service Pack. Nous vous recommandons de restaurer la sauvegarde sur un serveur de secours afin que ce système soit immédiatement disponible en cas de problème.

  - **La mise à jour cumulative est déployée**   l’équipe de l’administrateur Lync effectue l’installation pendant le cycle de maintenance planifiée.

<div>

## <a name="managing-the-timing-of-changes"></a>Gestion du calendrier des modifications

Nous vous recommandons d’implémenter une procédure pour les modifications de planification afin d’éviter toute interruption dans les sections de votre travail qui se chevauchent. Par exemple, deux équipes peuvent à la fois planifier un changement mineur sur un système. Il est possible qu’une équipe applique une mise à jour cumulative sur un pool pendant qu’une autre équipe migre des utilisateurs hérités vers ce pool. Aucune des équipes n’est affectée par les modifications que l’autre équipe envisage, et chaque équipe n’est pas nécessairement informée des modifications que l’autre équipe prévoit. Si les deux modifications ont été effectuées en même temps, il peut y avoir des problèmes d’implémentation des modifications. En outre, si des problèmes surviennent après l’application des modifications, par exemple, en cas d’échec de la migration de l’utilisateur, il peut s’avérer difficile de déterminer le changement à restaurer. Des périodes de maintenance régulières doivent être configurées entre le service informatique et la direction pour tester les modifications et les accepter.

</div>

</div>

<span> </span>

</div>

</div>

</div>

