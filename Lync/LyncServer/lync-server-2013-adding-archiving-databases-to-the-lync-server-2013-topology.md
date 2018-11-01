---
title: Ajout de bases de données d’archivage à la topologie Lync Server 2013
TOCTitle: Ajout de bases de données d’archivage à la topologie Lync Server 2013
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204654(v=OCS.15)
ms:contentKeyID: 49296171
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ajout de bases de données d’archivage à la topologie Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-10_

Vous devez incorporer l’archivage dans votre topologie avant de configurer votre déploiement pour qu’il prenne en charge l’archivage. Les informations de cette rubrique expliquent comment utiliser le Générateur de topologie pour ajouter l’archivage à votre topologie.

> [!NOTE]  
> Si vous voulez utiliser l’intégration Microsoft Exchange pour stocker les données et les fichiers d’archivage sur les serveurs Exchange 2013 pour tous les utilisateurs de votre déploiement, ne fournissez aucune information pour <strong>Magasin SQL Server d’archivage</strong> ou <strong>Utiliser la mise en miroir du magasin SQL Server</strong>.

## Pour ajouter la prise en charge de la base de données d’archivage à votre topologie

1.  Sur un ordinateur exécutant Lync Server 2013 ou sur lequel les outils d’administration Lync Server sont installés, ouvrez une session à l’aide d’un compte membre du groupe local Utilisateurs (ou disposant de droits d’utilisateur équivalents).
    
    > [!NOTE]  
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe local Utilisateurs, mais pour la publier, ce qui est nécessaire pour ajouter un serveur à la topologie, vous devez utiliser un compte membre du groupe <strong>Administrateurs de domaine</strong> et du groupe <strong>RTCUniversalServerAdmins</strong> et qui dispose d’autorisations de contrôle complètes (lecture, écriture et modification) sur le partage de fichiers que vous utilisez pour le magasin de fichiers Lync Server 2013 (pour que le Générateur de topologie puisse configurer les listes de contrôle d’accès discrétionnaires requises), ou un compte disposant de droits équivalents.

2.  Démarrez le Générateur de topologie.

3.  Dans l’arborescence de la console, accédez au pool frontal dans lequel vous voulez déployer l’archivage, puis cliquez sur le nom de ce pool frontal.

4.  Dans le menu **Action**, cliquez sur **Modifier les propriétés**.

5.  Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **Général**.

6.  Faites défiler la liste jusqu’à **Archivage**.

7.  Activez la case à cocher **Archivage**.

8.  Sous **Magasin SQL Server d’archivage,** effectuez l’une des opérations suivantes :
    
      - Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser. Si tous les utilisateurs sont hébergés sur Microsoft Exchange Server 2013 ou version ultérieure, vous pouvez archiver les communications Lync pour tous les utilisateurs dans Exchange. Dans ce cas, vous n’avez pas besoin de configurer le magasin d’archivage SQL Server.
    
      - Pour spécifier un nouveau magasin SQL Server, cliquez sur **Nouveau**, puis dans la boîte de dialogue **Définir un nouveau magasin SQL Server**, procédez comme suit :
        
          - Dans **Nom de domaine complet SQL Server**, spécifiez le nom de domaine complet du serveur sur lequel vous voulez créer le nouveau magasin SQL Server.
        
          - Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut, ou, pour spécifier une autre instance, cliquez sur **Instance nommée**, puis spécifiez l’instance que vous voulez utiliser.
        
          - Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **Cette instance SQL fait partie d’une relation de mise en miroir** puis, dans **Numéro de port du miroir**, spécifiez le numéro de port.

9.  Si vous voulez utiliser la mise en miroir du magasin SQL Server, sélectionnez **Activer la mise en miroir du magasin SQL Server**, puis procédez comme suit :
    
      - Pour utiliser un magasin SQL Server existant pour la mise en miroir, dans la zone de liste déroulante **Miroir du magasin SQL Server d’archivage**, cliquez sur le nom du magasin SQL Server que vous voulez utiliser pour la mise en miroir.
    
      - Pour spécifier un nouveau magasin SQL Server pour la mise en miroir, cliquez sur **Nouveau**, puis dans la boîte de dialogue **Définir un nouveau magasin SQL Server**, effectuez l’une des opérations suivantes :
        
        1.  Dans **Nom de domaine completSQL Server**, spécifiez le nom de domaine complet du serveur SQL Server sur lequel vous voulez créer le nouveau magasin SQL Server.
        
        2.  Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut, ou, pour définir une autre instance, cliquez sur **Instance nommée**, puis spécifiez l’instance à utiliser.
        
        3.  Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **Cette instance SQL fait partie d’une relation de mise en miroir** puis, dans **Numéro de port du miroir**, spécifiez le numéro de port.
    
      - Si vous activez la mise en miroir SQL Server et voulez inclure un témoin de mise en miroir SQL Server (une troisième instance SQL Server distincte pouvant détecter l’état du serveur SQL Server principal et les instances de miroir), activez la case à cocher **Utiliser le témoin de mise en miroir SQL Server pour activer le basculement automatique**, puis effectuez l’une des opérations suivantes :
        
        1.  Dans **Nom de domaine complet SQL Server**, spécifiez le nom de domaine complet du serveur sur lequel vous voulez créer le nouveau témoin de mise en miroir SQL Server.
        
        2.  Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut, ou, pour définir une autre instance, cliquez sur **Instance nommée**, puis spécifiez l’instance à utiliser comme témoin de mise en miroir.
        
        3.  Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **Cette instance SQL fait partie d’une relation de mise en miroir** puis, dans **Numéro de port du miroir**, spécifiez le numéro de port.

10. Pour enregistrer la configuration, cliquez sur **OK**.

