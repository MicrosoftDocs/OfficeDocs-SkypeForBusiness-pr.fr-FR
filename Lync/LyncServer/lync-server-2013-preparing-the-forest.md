---
title: 'Lync Server 2013 : Préparation de la forêt'
TOCTitle: Préparation de la forêt
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425898(v=OCS.15)
ms:contentKeyID: 49296963
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Préparation de la forêt pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

La préparation d’une forêt consiste à créer les paramètres et objets globaux Active Directory, ainsi que les groupes universels Active Directory afin de les rendre utilisables par Lync Server 2013 ; cette opération permet également d’accorder les autorisations d’accès appropriées aux objets Active Directory. Pour une description des groupes universels, ainsi que des paramètres et objets globaux créés à l’issue de la préparation de la forêt, reportez-vous à [Modifications effectuées par la préparation de la forêt dans Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).

Cette étape crée également des objets contenant des jeux de propriétés et des spécificateurs d’affichage utilisés par Lync Server 2013 et les stocke dans le conteneur de configuration.

> [!IMPORTANT]  
> Vérifiez que les modifications de schéma ont été répliquées sur tous les autres contrôleurs de domaine avant d’effectuer la procédure de préparation de forêt. Une erreur se produit si la réplication n’est pas terminée.

Si vous procédez à un nouveau déploiement de Lync Server, vous devez stocker les paramètres globaux dans le conteneur de configuration. Si vous procédez à une mise à niveau à partir d’une version antérieure et que vous continuez de stocker les paramètres globaux dans le conteneur système, vous pouvez continuer d’utiliser ce dernier.

Pour effectuer cette procédure, vous devez être membre du groupe Administrateurs d’entreprise ou Administrateurs de domaine pour le domaine racine de la forêt.

## Dans cette section

  - [Exécution de la préparation de la forêt pour Lync Server 2013](lync-server-2013-running-forest-preparation.md)

  - [Utilisation des commandes d’applet pour inverser la préparation d’une forêt pour Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

