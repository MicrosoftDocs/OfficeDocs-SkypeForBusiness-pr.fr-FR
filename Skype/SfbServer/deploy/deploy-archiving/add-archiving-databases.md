---
title: Ajouter des bases de données d’archivage à un déploiement existant dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Résumé: cette rubrique vous explique comment ajouter des bases de données d’archivage à votre déploiement Skype entreprise Server.'
ms.openlocfilehash: b7d429206e003042922b9b9cae6de420fdf517bb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234374"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>Ajouter des bases de données d’archivage à un déploiement existant dans Skype entreprise Server
 
**Résumé:** Consultez cette rubrique pour découvrir comment ajouter des bases de données d’archivage à votre déploiement de Skype entreprise Server.
  
Vous devez incorporer l’archivage dans votre topologie avant de configurer votre déploiement pour qu’il prenne en charge l’archivage. Les informations contenues dans cet article vous expliquent comment utiliser le générateur de topologie pour:
  
- Ajouter une base de données d’archivage à votre topologie.
    
- Publiez la topologie mise à jour pour ajouter la base de données d’archivage à votre déploiement de Skype entreprise Server.
    
> [!NOTE]
> Si vous souhaitez utiliser l’intégration de Microsoft Exchange pour stocker les données et fichiers d’archivage sur les serveurs Exchange pour tous les utilisateurs de votre déploiement, ne spécifiez pas **l’archivage de SQL Server Store** ou les informations de **mise en miroir SQL Server Store** .
  
### <a name="add-an-archiving-database-to-your-topology"></a>Ajouter une base de données d’archivage à votre topologie

1. Sur un ordinateur exécutant Skype entreprise Server ou sur lequel sont installés les outils d’administration de Skype entreprise Server, connectez-vous à l’aide d’un compte membre du groupe utilisateurs locaux (ou d’un compte possédant des droits d’utilisateur similaires).
    
2. Démarrer le générateur de topologie.
    
3. Dans l’arborescence de la console, accédez au pool frontal dans lequel vous voulez déployer l’archivage, puis cliquez sur le nom de ce pool frontal.
    
4. Dans le menu **Action**, cliquez sur **Modifier les propriétés**. 
    
5. Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **Général**.
    
6. Faites défiler la liste jusqu’à **Archivage**.
    
7. Activez la case à cocher **Archivage**.
    
8. Sous **archivage de SQL Server Store,** effectuez l’une des opérations suivantes:
    
   - Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser. Si tous vos utilisateurs sont hébergés sur Microsoft Exchange Server 2013 ou une version ultérieure, vous pouvez archiver les communications Skype entreprise pour tous vos utilisateurs en échange. Dans ce cas, vous n’avez pas besoin de configurer le magasin SQL Server d’archivage.
    
   - Pour spécifier un nouveau SQL Server Store, cliquez sur **nouveau**puis, dans la boîte de dialogue **définir un nouveau SQL Server Store** , procédez comme suit:
    
   - Dans **FQDN SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur sur lequel vous souhaitez créer le nouveau SQL Server Store.
    
   - Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.
    
   - Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans une relation en miroir** , puis, dans numéro de port **en miroir**, spécifiez le numéro de port.
    
9. Si vous souhaitez utiliser la mise en miroir SQL Server Store, sélectionnez **activer la mise en miroir SQL Server Store**, puis procédez comme suit:
    
   - Pour utiliser un magasin SQL Server existant pour la mise en miroir, dans la zone de liste déroulante archivage de **SQL Server Store** , cliquez sur le nom du magasin SQL Server que vous voulez utiliser pour la mise en miroir.
    
   - Pour spécifier un nouveau magasin SQL Server pour la mise en miroir, cliquez sur **nouveau**puis, dans la boîte de dialogue **définir un nouveau SQL Server Store** , effectuez l’une des opérations suivantes:
    
     a. Dans **nom de domaine complet SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur SQL sur lequel vous souhaitez créer le nouveau SQL Server Store.
    
     b. Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.
    
     c. Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans une relation en miroir** , puis, dans numéro de port **en miroir**, spécifiez le numéro de port.
    
   - Si vous activez la mise en miroir SQL Server et souhaitez inclure un témoin de mise en miroir SQL Server (troisième instance SQL Server distincte capable de détecter l’état du serveur SQL Server et des instances miroir principales), sélectionnez le **témoin de mise en miroir SQL Server pour activer le service automatique. **activez le basculement, puis effectuez l’une des opérations suivantes:
    
     a. Dans **FQDN SQL Server**, spécifiez le nom de domaine complet (FQDN) du serveur sur lequel vous souhaitez créer le nouveau témoin de mise en miroir SQL Server.
    
     b. Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser comme témoin de mise en miroir.
    
     c. Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, activez la case à cocher **cette instance SQL est dans une relation en miroir** , puis, dans numéro de port **en miroir**, spécifiez le numéro de port.
    
10. Pour enregistrer la configuration, cliquez sur **OK**.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>Publier la topologie mise à jour pour ajouter une base de données d’archivage à votre déploiement

1. Sur un ordinateur exécutant Skype entreprise Server ou sur lequel sont installés les outils d’administration de Skype entreprise Server, connectez-vous à l’aide d’un compte qui est membre du groupe utilisateurs local (ou d’un compte disposant de droits d’utilisateur équivalents).
    
    > [!NOTE]
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe utilisateurs locaux, mais pour publier une topologie, qui est nécessaire pour ajouter un serveur à la topologie, vous devez utiliser un compte membre du groupe **administrateurs de domaine** et de la **RTCUniversalServer. Groupe administrateurs** et qui dispose des autorisations contrôle total (lecture, écriture et modification) sur le partage de fichiers que vous utilisez pour le stockage de fichiers Skype entreprise Server (de sorte que le générateur de topologie puisse configurer la liste de contrôle d’accès discrétionnaire (DACL) requise ou un compte avec des droits équivalents.
  
2. Ouvrez la topologie que vous avez créée dans la section précédente à l’aide du générateur de topologie.
    
3. Dans l’arborescence de la console, cliquez avec le bouton droit sur **Skype entreprise Server**, puis cliquez sur **publier la topologie**.
    
4. Dans la page **Publier la topologie**, cliquez sur **Suivant**.
    
5. Dans la page **Créer des bases de données**, vérifiez que la base de données est sélectionnée, puis cliquez sur **Suivant**. 
    
    > [!NOTE]
    > Si vous ne disposez pas des autorisations appropriées pour créer des bases de données, vous pouvez annuler la sélection de la base de données et laisser une autre personne dotée des autorisations nécessaires la créer. > seules les bases de données sur des serveurs SQL dédiés peuvent être installées à l’aide du générateur de topologie. Les bases de données situées sur des serveurs SQL colocalisés avec d’autres composants serveur doivent être installées via une installation locale sur l’ordinateur concerné. 
  
6. Dans la page **Assistant Publication terminé**, assurez-vous que la topologie a été publiée correctement, puis cliquez sur **Terminer**.
    
    > [!IMPORTANT]
    > Une fois la topologie publiée, vous devez configurer les options et les stratégies relatives à l’archivage pour permettre l’archivage du contenu. Pour plus d’informations, reportez-vous à la rubrique [Configuration des options d’archivage de Skype entreprise Server](configure-archiving-options.md) et [Configuration des stratégies d’archivage de Skype entreprise Server](configure-archiving-policies.md). 
  

