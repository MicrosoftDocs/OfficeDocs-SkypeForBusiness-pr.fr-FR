---
title: "Publication de la topologie màj pour l’ajout des bases de données d’archivage"
TOCtitle: "Publication de la topologie màj pour l’ajout des bases de données d’archivage"
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204860(v=OCS.15)
ms:contentKeyID: 49297064
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Publication de la topologie mise à jour pour l’ajout des bases de données d’archivage

 

_**Dernière rubrique modifiée :** 2012-10-01_

Après avoir mis à jour votre topologie dans le Générateur de topologie, vous devez la publier dans le magasin central de gestion pour pouvoir configurer et utiliser l’archivage. Les copies en lecture seule des données sont répliquées sur tous les serveurs de la topologie afin de maintenir la synchronisation de tous les serveurs avec la topologie et d’autres modifications intervenues dans la configuration.

## Pour publier votre topologie mise à jour

1.  Sur un ordinateur exécutant Lync Server 2013 ou sur lequel les outils d’administration Lync Server sont installés, ouvrez une session à l’aide d’un compte membre du groupe local Utilisateurs (ou disposant de droits d’utilisateur équivalents).
    
    > [!NOTE]  
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe local Utilisateurs, mais pour la publier, ce qui est nécessaire pour ajouter un serveur à la topologie, vous devez utiliser un compte membre du groupe <strong>Admins du domaine</strong> et du groupe <strong>RTCUniversalServerAdmins</strong> et qui dispose d’autorisations de contrôle complètes (lecture, écriture et modification) sur le partage de fichiers que vous utilisez pour le magasin de fichiers Lync Server 2013 (pour que le Générateur de topologie puisse configurer les listes de contrôle d’accès discrétionnaires nécessaires), ou un compte disposant de droits équivalents.

2.  Ouvrez la topologie que vous avez créée dans la section précédente à l’aide du Générateur de topologie.

3.  Dans l’arborescence de la console, cliquez avec le bouton droit sur **Lync Server 2013**, puis cliquez sur **Publier la topologie**.

4.  Dans la page **Publier la topologie**, cliquez sur **Suivant**.

5.  Dans la page **Créer des bases de données**, vérifiez que la base de données est sélectionnée, puis cliquez sur **Suivant**.
    
    > [!NOTE]  
    > Si vous ne disposez pas des autorisations appropriées pour créer des bases de données, vous pouvez annuler la sélection de la base de données et laisser une autre personne dotée des autorisations nécessaires la créer. Pour plus d’informations sur les droits et les autorisations d’administrateur nécessaires, voir <a href="lync-server-2013-deployment-permissions-for-sql-server.md">Autorisations de déploiement de SQL Server dans Lync Server 2013</a> dans la documentation de déploiement.<br />
    Seules les bases de données résidant sur des serveurs SQL Server dédiés peuvent être installées à l’aide du Générateur de topologie. Les bases de données situées sur des serveurs SQL Server colocalisés avec d’autres composants serveur doivent être installées via une installation locale sur l’ordinateur concerné.

6.  Dans la page **Assistant Publication terminé**, assurez-vous que la topologie a été publiée correctement, puis cliquez sur **Terminer**.
    
    > [!IMPORTANT]  
    > Une fois la topologie publiée, vous devez configurer les options et les stratégies relatives à l’archivage pour permettre l’archivage du contenu. Pour plus d’informations, voir <a href="lync-server-2013-configuring-support-for-archiving.md">Configuration de la prise en charge de l’archivage dans Lync Server 2013</a> dans la documentation de déploiement.
