---
title: Ajouter des bases de données d’archivage à un déploiement existant dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Résumé : Lisez cette rubrique pour savoir comment ajouter des bases de données d’archivage à votre Skype pour le déploiement de serveur d’entreprise.'
ms.openlocfilehash: 083b6329cdf27331ba861b96a74f94e2ae5aa912
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895313"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>Ajouter des bases de données d’archivage à un déploiement existant dans Skype pour Business Server
 
**Résumé :** Lisez cette rubrique pour savoir comment ajouter des bases de données d’archivage à votre Skype pour le déploiement de serveur d’entreprise.
  
Vous devez incorporer l’archivage dans votre topologie avant de configurer votre déploiement pour qu’il prenne en charge l’archivage. Les informations contenues dans cette rubrique expliquent comment utiliser le Générateur de topologie pour :
  
- Ajouter une base de données d’archivage à votre topologie.
    
- Publier la topologie mise à jour pour ajouter la base de données d’archivage à votre Skype pour le déploiement de serveur d’entreprise.
    
> [!NOTE]
> Si vous souhaitez utiliser l’intégration de Microsoft Exchange pour stocker les données d’archivage et de fichiers sur des serveurs Exchange pour tous vos utilisateurs dans votre déploiement, ne spécifiez pas les informations de **magasin SQL Server de l’archivage** ou **la mise en miroir d’utiliser un magasin SQL Server** .
  
### <a name="add-an-archiving-database-to-your-topology"></a>Ajouter une base de données d’archivage à votre topologie

1. Sur un ordinateur qui exécute Skype pour Business Server ou sur lequel le Skype pour les outils d’administration Business Server sont installés, ouvrez une session en utilisant un compte qui est membre du groupe utilisateurs local (ou un compte disposant de droits utilisateur équivalents).
    
2. Démarrez le Générateur de topologie.
    
3. Dans l’arborescence de la console, accédez au pool frontal dans lequel vous voulez déployer l’archivage, puis cliquez sur le nom de ce pool frontal.
    
4. Dans le menu **Action**, cliquez sur **Modifier les propriétés**. 
    
5. Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **Général**.
    
6. Faites défiler la liste jusqu’à **Archivage**.
    
7. Activez la case à cocher **Archivage**.
    
8. Sous **magasin de SQL Server d’archivage,** effectuez l’une des options suivantes :
    
   - Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser. Si tous les utilisateurs sont hébergés sur Microsoft Exchange Server 2013 ou au-dessus, vous pouvez archiver Skype pour les communications d’entreprise pour tous vos utilisateurs dans Exchange. Dans ce cas, vous n’avez pas besoin de configurer le service banque d’archivage de serveur SQL.
    
   - Pour spécifier un nouveau magasin SQL Server, cliquez sur **Nouveau**, puis dans la boîte de dialogue **Définir nouveau magasin SQL Server** , procédez comme suit :
    
   - Dans **Nom de domaine complet de SQL Server**, spécifiez le nom de domaine complet du serveur sur lequel vous souhaitez créer le nouveau magasin SQL Server.
    
   - Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.
    
   - Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL se trouve dans la relation de mise en miroir** , puis, dans le **numéro de port de mise en miroir**, spécifiez le numéro de port.
    
9. Si vous souhaitez utiliser la mise en miroir du magasin SQL Server, sélectionnez **la mise en miroir d’activer un magasin SQL Server**, puis procédez comme suit :
    
   - Pour utiliser un magasin SQL Server pour la mise en miroir, dans la zone de liste déroulante **miroir du magasin SQL Server d’archivage** , cliquez sur le nom du magasin SQL Server que vous souhaitez utiliser pour la mise en miroir.
    
   - Pour spécifier un nouveau magasin SQL Server pour la mise en miroir, cliquez sur **Nouveau**, puis dans la boîte de dialogue **Définir nouveau magasin SQL Server** , effectuez l’une des options suivantes :
    
     a. Dans **Nom de domaine complet de SQL Server**, spécifiez le nom de domaine complet du serveur SQL sur lequel vous souhaitez créer le nouveau magasin SQL Server.
    
     b. Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.
    
     c. Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL se trouve dans la relation de mise en miroir** , puis, dans le **numéro de port de mise en miroir**, spécifiez le numéro de port.
    
   - Si vous activez la mise en miroir SQL Server et que vous souhaitez inclure un témoin (une troisième et distincte instance SQL Server qui peut détecter l’intégrité des instances de SQL Server et miroir principales) de la mise en miroir de SQL Server, sélectionnez le **témoin de mise en miroir utiliser SQL Server pour activer automatique basculement** case à cocher, puis effectuez l’une des opérations suivantes :
    
     a. Dans **Nom de domaine complet de SQL Server**, spécifiez le nom de domaine complet du serveur sur lequel vous souhaitez créer le nouveau serveur SQL témoin de mise en miroir.
    
     b. Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser comme témoin de mise en miroir.
    
     c. Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL se trouve dans la relation de mise en miroir** , puis, dans le **numéro de port de mise en miroir**, spécifiez le numéro de port.
    
10. Pour enregistrer la configuration, cliquez sur **OK**.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>Publier la topologie mise à jour pour ajouter une base de données d’archivage à votre déploiement

1. Sur un ordinateur qui exécute Skype pour Business Server ou sur lequel le Skype pour les outils d’administration Business Server sont installés, ouvrez une session en utilisant un compte qui est membre du groupe utilisateurs local (ou un compte disposant de droits utilisateur équivalents).
    
    > [!NOTE]
    > Vous pouvez définir une topologie en utilisant un compte qui est un membre du groupe utilisateurs local, mais pour publier une topologie qui est nécessaire pour ajouter un serveur à la topologie, vous devez utiliser un compte qui est membre du groupe **Admins** du domaine et le **RTCUniversalServer Administrateurs** groupe et qui dispose d’autorisations Contrôle total (lire, écrire et modifier) sur le partage de fichiers que vous utilisez pour le Skype pour le magasin de fichiers Business Server (afin que le Générateur de topologie puisse configurer la liste de contrôle d’accès discrétionnaire requises (DACL), ou une compte disposant de droits équivalents.
  
2. Ouvrez la topologie que vous avez créé dans la section précédente à l’aide du Générateur de topologie.
    
3. Dans l’arborescence de la console, avec le bouton droit **Skype pour Business Server**, puis cliquez sur **Publier la topologie**.
    
4. Dans la page **Publier la topologie**, cliquez sur **Suivant**.
    
5. Dans la page **Créer des bases de données**, vérifiez que la base de données est sélectionnée, puis cliquez sur **Suivant**. 
    
    > [!NOTE]
    > Si vous ne disposez pas des autorisations appropriées pour créer des bases de données, vous pouvez annuler la sélection de la base de données et laisser une autre personne dotée des autorisations nécessaires la créer. > des bases de données uniquement sur les serveurs SQL dédié peuvent être installés à l’aide du Générateur de topologie. Les bases de données situées sur des serveurs SQL colocalisés avec d’autres composants serveur doivent être installées via une installation locale sur l’ordinateur concerné. 
  
6. Dans la page **Assistant Publication terminé**, assurez-vous que la topologie a été publiée correctement, puis cliquez sur **Terminer**.
    
    > [!IMPORTANT]
    > Une fois la topologie publiée, vous devez configurer les options et les stratégies relatives à l’archivage pour permettre l’archivage du contenu. Pour plus d’informations, voir [configurer les options de Skype pour Business Server d’archivage](configure-archiving-options.md) et de [configurer des stratégies pour Skype pour Business Server d’archivage](configure-archiving-policies.md). 
  

