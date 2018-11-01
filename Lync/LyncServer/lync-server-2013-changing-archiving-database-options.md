---
title: "Modif. des options de la base de données d’archivage dans Lync Server 2013"
TOCtitle: "Modif. des options de la base de données d’archivage dans Lync Server 2013"
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204814(v=OCS.15)
ms:contentKeyID: 49296868
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modification des options de la base de données d’archivage dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Si vous déployez l’archivage à l’aide du stockage SQL Server pour l’un de vos utilisateurs, vous pouvez apporter les modifications suivantes au stockage de la base de données :

  - Utilisez une autre base de données SQL Server pour le stockage de l’archivage. Il peut s’agir de la base de données d’archivage principale ou de toute base de données que vous utilisez pour la mise en miroir SQL Server.

  - Préférez l’intégration de Microsoft Exchange comme moyen de stocker les données et les fichiers d’archivage sur des serveurs Exchange 2013. Si tous vos utilisateurs sont hébergés sur vos serveurs Exchange 2013 et que vous voulez utiliser le stockage Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous devez supprimer les bases de données du magasin SQL Server de votre topologie.

Pour apporter l’une de ces modifications, vous devez exécuter le Générateur de topologie, effectuer les modifications et republiez la topologie. Vous pouvez utiliser le Générateur de topologie dans ce but. Ne spécifiez pas les informations relatives au **Magasin SQL Server d’archivage** ou à **Activer la mise en miroir du magasin SQL Server**, à moins que certains de vos utilisateurs Lync ne soient pas hébergés sur des serveurs Exchange 2013.

## Pour modifier vos options de base de données d’archivage

1.  Sur un ordinateur exécutant Lync Server 2013 ou sur lequel les outils d’administration Lync Server sont installés, ouvrez une session à l’aide d’un compte membre du groupe local Utilisateurs (ou disposant de droits d’utilisateur équivalents).
    
    > [!NOTE]  
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe local Utilisateurs, mais pour la publier, ce qui est nécessaire pour ajouter un serveur à la topologie, vous devez utiliser un compte membre du groupe <strong>Administrateurs de domaine</strong> et du groupe <strong>RTCUniversalServerAdmins</strong> et qui dispose d’autorisations de contrôle complètes (lecture, écriture et modification) sur le partage de fichiers que vous utilisez pour le magasin de fichiers Lync Server 2013 (pour que le Générateur de topologie puisse configurer les listes de contrôle d’accès discrétionnaires requises), ou un compte disposant de droits équivalents.

2.  Démarrez le Générateur de topologie.

3.  Dans l’arborescence de la console, accédez au pool de serveurs frontaux dans lequel vous avez déployé l’archivage, puis cliquez sur le nom du pool de serveurs frontaux dans lequel vous voulez modifier les options de base de données.

4.  Dans le menu **Action**, cliquez sur **Modifier les propriétés**.

5.  Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **Général**.

6.  Faites défiler la liste jusqu’à **Archivage**.

7.  Dans **Archivage**, procédez comme suit :
    
      - Pour choisir un autre magasin SQL Server existant, sous **Magasin SQL Server d’archivage**, dans la zone de liste déroulante, procédez comme suit :
        
          - Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.
        
          - Pour spécifier un nouveau magasin SQL Server, cliquez sur **Nouveau**, puis dans la boîte de dialogue **Définir un nouveau magasin SQL Server**, procédez comme suit :
            
              - Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser.
            
              - Pour spécifier un nouveau magasin SQL Server, cliquez sur **Nouveau**, puis dans la boîte de dialogue **Définir un nouveau magasin SQL Server**, procédez comme suit :
                
                  - Dans le champ **Nom de domaine complet du serveur SQL Server**, spécifiez le nom de domaine complet du serveur sur lequel vous souhaitez créer le nouveau magasin SQL Server.
                
                  - Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.
                
                  - Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **Cette instance SQL fait partie d’une relation de mise en miroir** puis, dans **Numéro de port du miroir**, spécifiez le numéro de port.
    
      - Pour ajouter le magasin SQL Server ou choisir un autre magasin SQL Server existant pour la mise en miroir, sélectionnez **Activer la mise en miroir du magasin SQL Server**, puis procédez comme suit :
        
          - Pour utiliser un magasin SQL Server existant pour la mise en miroir, dans la zone de liste déroulante **Miroir du magasin SQL d’archivage**, cliquez sur le nom du magasin SQL Server à utiliser pour la mise en miroir.
        
          - Pour spécifier un nouveau magasin SQL Server pour la mise en miroir, cliquez sur **Nouveau**, puis dans la boîte de dialogue **Définir un nouveau magasin SQL Server**, procédez de l’une des manières suivantes :
            
            1.  Dans le champ **Nom de domaine complet du serveur SQL Server**, spécifiez le nom de domaine complet du serveur SQL Server sur lequel vous souhaitez créer le nouveau magasin SQL Server.
            
            2.  Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser.
            
            3.  Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **Cette instance SQL fait partie d’une relation de mise en miroir** puis, dans **Numéro de port du miroir**, spécifiez le numéro de port.
        
          - Si vous activez la mise en miroir SQL Server et que vous voulez ajouter ou modifier un témoin de mise en miroir SQL Server (une troisième instance SQL Server distincte qui peut détecter l’intégrité du serveur SQL Server principal et mettre des instances en miroir), activez la case à cocher **Utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique**, puis procédez de l’une des manières suivantes :
            
            1.  Dans le champ **Nom de domaine complet du serveur SQL Server**, spécifiez le nom de domaine complet du serveur sur lequel vous souhaitez créer le nouveau témoin de mise en miroir SQL Server.
            
            2.  Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser comme témoin de mise en miroir.
            
            3.  Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **Cette instance SQL fait partie d’une relation de mise en miroir** puis, dans **Numéro de port du miroir**, spécifiez le numéro de port.
    
      - Pour choisir l’intégration de Microsoft Exchange comme moyen de stocker les données et fichiers d’archivage sur des serveurs Exchange 2013 (si tous les utilisateurs de votre déploiement sont hébergés sur vos serveurs Exchange 2013), supprimez toutes les informations des bases de données d’archivage.
    
    > [!IMPORTANT]  
    > Si vous avez des utilisateurs Lync qui ne sont pas hébergés sur des serveurs Exchange 2013, ne supprimez pas les informations du magasin SQL Server.

8.  Pour enregistrer la configuration, cliquez sur **OK**.
    
    > [!IMPORTANT]  
    > Les modifications apportées dans le Générateur de topologie ne prennent effet que quand vous publiez la nouvelle topologie. Pour plus d’informations, voir <a href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Publication de la topologie mise à jour pour l’ajout des bases de données d’archivage</a> dans la documentation de déploiement.
