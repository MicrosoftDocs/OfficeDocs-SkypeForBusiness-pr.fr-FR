---
title: "Lync Server 2013 : Install. de la base de données de serveur Standard Edition"
TOCTitle: Installation de la base de données de serveur Standard Edition
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398167(v=OCS.15)
ms:contentKeyID: 49296224
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installation de la base de données de serveur Standard Edition pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-01_

L’installation d’un serveur Standard Edition comme seul serveur dans votre infrastructure qui héberge des utilisateurs diffère de celle des autres serveurs, car vous devez sélectionner une option spéciale dans l’**Assistant Déploiement** pour installer ce serveur.

## Pour installer un serveur Standard Edition

1.  Connectez-vous au serveur sur lequel vous allez installer le serveur Standard Edition en tant qu’administrateur local ou avec un domaine équivalent.

2.  Si vous n’avez pas préparé les services de domaine Active Directory, effectuez d’abord ces procédures. Pour plus d’informations, reportez-vous à [Préparation des services de domaine Active Directory pour Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

3.  Dans l’Assistant Déploiement de Lync Server, cliquez sur **Préparer d’abord le serveur Standard Edition** .

4.  Dans la page **Préparer le serveur Standard Edition** , cliquez sur **Suivant** .

5.  Dans la page **Exécution de commandes** , le logiciel de base de données SQL Server 2012 Express est installé en tant que magasin central de gestion. Les règles de pare-feu nécessaires sont créées. Lorsque l’installation de la base de données et des logiciels prérequis est terminée, cliquez sur **Terminer** .
    
    > [!NOTE]  
    > L’installation initiale peut durer un certain temps sans que les mises à jour ne soient visibles sur l’écran récapitulatif des résultats de la commande. Cela est dû à l’installation de SQL Server Express. Pour surveiller l’installation de la base de données, utilisez le Gestionnaire des tâches.

6.  Dans la page de l’Assistant Déploiement de Lync Server, cliquez sur **Installer le générateur de topologie** si vous n’avez pas déjà installé les outils d’administration. Pour plus d’informations, reportez-vous à [Installation des outils d’administration Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md).

7.  Vérifiez que des coches vertes s’affichent bien en regard de « Préparer Active Directory », « Préparer le serveur Standard Edition » et « Installer le générateur de topologie ».

