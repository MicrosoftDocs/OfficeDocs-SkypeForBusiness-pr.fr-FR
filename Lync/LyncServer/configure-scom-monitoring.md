---
title: Configuration de la surveillance SCOM
TOCTitle: Configuration de la surveillance SCOM
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49891321
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la surveillance SCOM

 

_**Dernière rubrique modifiée :** 2012-10-04_

Après avoir migré vers Microsoft Lync Server 2013, vous devez effectuer certaines tâches de configuration pour permettre à Lync Server 2013 de fonctionner avec System Center Operations Manager.

  - Appliquez les mises à jour de Lync Server 2010 à un serveur dédié à la gestion de la logique de détection centrale.

  - Mettez à jour la clé de Registre du serveur candidat de détection centrale.

  - Configurez votre serveur d’administration principal System Center Operations Manager pour remplacer le nœud candidat de détection centrale.

Des instructions pour mener à bien chacune de ces tâches sont fournies ci-dessous.

**Appliquez les mises à jour de Lync Server 2010 à un serveur dédié à la gestion de la logique de détection centrale.**

1.  Choisissez un serveur sur lequel les fichiers de l’agent System Center Operations Manager sont installés et qui est configuré en tant que nœud candidat de détection centrale.

2.  Appliquez les mises à jour de Lync Server 2010 à ce serveur. Reportez-vous à la rubrique [Application des mises à jour Lync Server 2010](apply-lync-server-2010-updates.md).

**Mettez à jour la clé de Registre du serveur candidat de détection centrale.**

1.  Sur le serveur dédié à la gestion de la logique de détection centrale, ouvrez une fenêtre de commande Windows PowerShell.

2.  Dans la ligne de commande, tapez ce qui suit :
    
    ```
    New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
    ```
    ```
    New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
    ```
    
    > [!NOTE]  
    > À chaque modification du Registre, une erreur liée à l’échec de la commande risque de se produire si la clé de Registre existe déjà. Dans ce cas, vous pouvez ignorer cette erreur sans risque.

**Configurez votre serveur d’administration principal System Center Operations Manager pour remplacer le nœud observateur candidat de détection centrale.**

1.  Sur un ordinateur doté de la console System Center Operations Manager, développez **Objets du pack d’administration**, puis sélectionnez **Détections d’objets**.

2.  Cliquez sur **Modifier l’étendue...**.

3.  Dans la page **Étendre les objets du pack d’administration**, sélectionnez **Candidat de détection LS**.

4.  Remplacez la **Valeur effective du candidat de détection LS** par le nom du serveur candidat choisi dans la procédure précédente.

Enfin, pour finaliser vos modifications, redémarrez le service de contrôle d’intégrité sur le serveur d’administration racine System Center Operations Manager.

