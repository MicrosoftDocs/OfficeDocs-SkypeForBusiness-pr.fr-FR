---
title: 'Lync Server 2013: gestion des modifications'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Change management
ms:assetid: 73c774f5-c12f-4c72-be73-e07dc745b994
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720336(v=OCS.15)
ms:contentKeyID: 63969618
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13eb521ea6b4be5f8d701885df65a3e1672b2eaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-management-in-lync-server-2013"></a>Gestion des modifications dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-08-18_

La modification de l’environnement informatique est inévitable. Les modifications incluent de nouvelles technologies, systèmes, applications, matériel, outils, processus et modifications dans les rôles et les responsabilités. Un système de gestion des modifications efficace vous permet d’apporter des modifications à l’environnement informatique en toute simplicité et en minimisant les interruptions de service. Un système de gestion des modifications réunit les équipes impliquées dans le changement de système. Par exemple, en choisissant de tirer parti d’Office Web Apps. Il s’agit d’une application de service Lync intégrée qui permet aux utilisateurs de lire et de modifier des documents dans un navigateur. La mise en place de ce service, une fois que vous êtes passé en production, nécessite la participation de plusieurs équipes:

  - **Test**   de l’équipe cette équipe charge les tests sur Office Web Apps sur un serveur de test, dans le processus fournissant des informations sur les modèles d’utilisation prévus et les performances attendues des serveurs de production.

  - **Administrateurs Lync cette**   équipe détermine la stratégie de déploiement et l’installation à l’endroit où il était possible. L’équipe doit s’assurer que le changement est déployé dans l’environnement de production et qu’il est responsable de l’administration par la suite. L’équipe doit comprendre l’impact des modifications et les inclure dans les procédures avant que les modifications soient apportées à la production.

  - **Équipe réseau cette**   équipe est responsable des modifications apportées aux règles de pare-feu qui autorisent l’accès à partir d’Internet aux serveurs de pools Lync internes. L’équipe est également responsable de l’utilisation des administrateurs Lync pour s’assurer que la bande passante disponible peut prendre en charge la charge supplémentaire.

  - **Équipe de sécurité**   cette équipe évalue la sécurité et réduit les risques. L’équipe de sécurité doit revoir les vulnérabilités connues et garantir le minimum de risques en matière de sécurité.

  - **Équipe d’approbation des utilisateurs**   cette équipe est composée d’utilisateurs qui souhaitent tester le système et formuler des commentaires sur les améliorations apportées.

Le processus de gestion des modifications définit les responsabilités de chaque équipe et planifie le travail à effectuer, en incluant des contrôles et des tests là où ils sont nécessaires. Les contrôles de modification varient en fonction de la complexité et de l’effet attendu d’une modification. Ils peuvent varier en fonction de l’approbation automatique des modifications mineures, de la modification des réunions de révision et des avis complets au niveau du projet. Pour en expliquer davantage, les groupes de modifications sont décrits dans cette section.

  - **Modifications**   majeures les modifications majeures ont un effet global sur le système et peuvent nécessiter une entrée de diverses équipes. Voici un exemple de mise à niveau vers Lync Server 2013. Les modifications majeures affectent de nombreuses équipes et peut-être des systèmes différents. Le processus de gestion des modifications inclura probablement une ou plusieurs réunions d’avis de modification pour informer les équipes participant au changement ou affectées par le changement.

  - **Modifications importantes les**   changements importants nécessitent des ressources significatives pour la planification, la création et l’implémentation. Des contrôles de modification appropriés doivent être introduits pour s’assurer que l’effet du changement est compris, que les procédures de déploiement sont testées et que les plans de restauration et de contingence sont prêts. Le déploiement d’une nouvelle mise à jour cumulative est un exemple de modification notable.

  - **Changements**   mineurs les changements mineurs n’affectent pas de façon significative l’environnement informatique, par exemple, en modifiant certaines stratégies Lync via le panneau de configuration Microsoft Lync Server 2013.

  - **Les**   modifications standard apportées aux modifications standard sont effectuées régulièrement et sont bien entendues et documentées. Le processus de gestion des modifications doit examiner toutes les modifications apportées aux procédures. Il n’est pas nécessaire de procéder à des modifications de routine comme la création d’une base de données de contenu ou l’ajout d’un utilisateur.

Dans l’exemple suivant, la gestion des modifications examine le mode d’interaction des différentes équipes et les actions effectuées lors du déploiement d’un nouveau Service Pack. Ces actions sont organisées et gérées par le processus de gestion des modifications.

  - **Déclenchement d’une demande**   de modification l’équipe de sécurité a évalué le dernier Service Pack et confirme qu’il résout une vulnérabilité dans le système de production. L’équipe déclenche une demande de modification pour que la nouvelle mise à jour cumulative s’applique à tous les serveurs exécutant Lync Server.

  - **Notes de publication du Service Pack examinez**   l’équipe de l’administrateur Lync qui examine les notes de publication du Service Pack pour identifier l’effet sur le système.

  - **Une série de tests en laboratoire est effectuée**   l’équipe de l’administrateur de Lync doit effectuer des mises à jour de test sur un serveur dans un environnement de test pour déterminer si le Service Pack peut être appliqué correctement sans affecter les applications et serveurs installés. dispositifs. S’il existe des applications tierces ou créées en interne qui interservent le serveur Lync dans un environnement de production, celles-ci doivent également être testées. Ces tests peuvent également être utilisés pour estimer le temps nécessaire pour effectuer les mises à jour.

  - **Les utilisateurs sont informés de la**   mise en place de l’équipe d’administration de Lync, de l’équipe de communication ou du Bureau d’aide de l’utilisateur, qui informe tous les utilisateurs concernés du cycle de maintenance planifié et de la durée d’indisponibilité du service.

  - **Une sauvegarde complète de Lync est effectuée avant**   de procéder à la mise à niveau de l’équipe de l’administrateur Lync pour vérifier qu’il existe une sauvegarde valide qui peut être utilisée pour rétablir l’état du système d’origine en cas d’échec de l’installation du Service Pack. Nous vous recommandons de restaurer la sauvegarde sur un serveur de secours pour que ce système soit facilement disponible en cas de problème.

  - **La mise à jour cumulative est déployée**   l’équipe de l’administrateur de Lync effectue l’installation pendant le cycle de maintenance planifiée.

<div>

## <a name="managing-the-timing-of-changes"></a>Gestion de la durée des modifications

Nous vous recommandons d’implémenter une procédure pour la planification des modifications afin d’éviter toute interruption dans les sections qui se chevauchent. Par exemple, il est possible que deux équipes envisagent une modification mineure d’un système. Une équipe peut appliquer une mise à jour cumulative sur un pool alors qu’une autre équipe migre des utilisateurs hérités vers ce pool. Aucune équipe n’est concernée par les modifications que l’autre équipe planifie, et chaque équipe ne connaît peut-être pas nécessairement les modifications que l’autre équipe planifie. Si les deux modifications ont été apportées en même temps, il est possible que les modifications soient implémentées. Par ailleurs, s’il y a des problèmes une fois les modifications appliquées (par exemple, en cas d’échec de la migration des utilisateurs), il peut être difficile de déterminer quelles modifications doivent être répercutées. Des périodes de maintenance normales doivent être définies entre le service informatique et la gestion pour tester les modifications et les accepter.

</div>

</div>

<span> </span>

</div>

</div>

</div>

