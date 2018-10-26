---
title: "Lync Server 2013 : Conf. requise pour l’infrastructure Active Directory"
TOCTitle: Configuration requise pour l’infrastructure Active Directory
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412955(v=OCS.15)
ms:contentKeyID: 49298760
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration requise pour l’infrastructure Active Directory pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Avant d’entamer le processus de préparation des services de domaine Active Directory pour Lync Server 2013, assurez-vous que votre infrastructure Active Directory présente la configuration requise suivante :

  - Tous les contrôleurs de domaine (comprenant l’ensemble des serveurs de catalogue global) dans la forêt où vous déployez Lync Server exécutent l’un des systèmes d’exploitation suivants :
    
      - Système d’exploitation Windows Server 2012 R2
    
      - Système d’exploitation Windows Server 2012
    
      - système d’exploitation Windows Server 2008 R2
    
      - système d’exploitation Windows Server 2008
    
      - Windows Server 2008 Enterprise 32 bits
    
      - Version 32 bits ou 64 bits du système d’exploitation Windows Server 2003 R2
    
      - Versions 32 ou 64 bits du système d’exploitation Windows Server 2003

  - Tous les domaines dans lesquels vous déployez Lync Server sont élevés à un niveau fonctionnel de domaine de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou au minimum Windows Server 2003.

  - La forêt dans laquelle vous déployez Lync Server est élevée à un niveau fonctionnel de forêt de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou au minimum Windows Server 2003.
    
    > [!NOTE]  
    > Pour modifier le niveau fonctionnel de votre domaine ou de votre forêt, reportez-vous à l’article « Augmentation des niveaux fonctionnels des domaines et des forêts » à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=263775" class="uri">http://go.microsoft.com/fwlink/?linkid=263775</a>

  - Un catalogue global est déployé dans tous les domaines dans lesquels vous déployez des ordinateurs ou des utilisateurs Lync Server.

Lync Server 2013 prend en charge les groupes universels dans les systèmes d’exploitation Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 et Windows Server 2003. Les membres des groupes universels peuvent comprendre d’autres groupes et comptes issus d’un domaine quelconque de l’arborescence de domaine ou de la forêt. Il est possible de leur attribuer des autorisations dans n’importe quel domaine de l’arborescence de domaine ou de la forêt. Associée à la délégation des tâches d’administration, la prise en charge des groupes universels simplifie la gestion d’un déploiement de Lync Server. Ainsi, pour qu’un administrateur puisse gérer deux domaines, il n’est pas nécessaire d’ajouter un domaine à un autre.

