---
title: Ajouter des bases de données d’archivage à un déploiement existant dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 'Résumé : Lisez cette rubrique pour découvrir comment ajouter des bases de données d’archivage à votre déploiement Skype Entreprise Server.'
ms.openlocfilehash: f7642cb79f73ab519938ddcb680f8450347b943d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820674"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>Ajouter des bases de données d’archivage à un déploiement existant dans Skype Entreprise Server
 
**Résumé :** Lisez cette rubrique pour découvrir comment ajouter des bases de données d’archivage à votre déploiement Skype Entreprise Server.
  
Vous devez incorporer l’archivage dans votre topologie avant de configurer votre déploiement pour qu’il prenne en charge l’archivage. Les informations de cette rubrique expliquent comment utiliser le Générateur de topologie pour :
  
- Ajoutez une base de données d’archivage à votre topologie.
    
- Publiez la topologie mise à jour pour ajouter la base de données d’archivage à votre déploiement Skype Entreprise Server.
    
> [!NOTE]
> Si vous souhaitez utiliser l’intégration De Microsoft Exchange pour stocker des données d’archivage et des fichiers sur des serveurs Exchange pour tous vos utilisateurs dans votre déploiement, ne spécifiez pas le magasin **d’archivage SQL Server** ou utilisez les informations de mise en miroir du **SQL Server Store.**
  
### <a name="add-an-archiving-database-to-your-topology"></a>Ajouter une base de données d’archivage à votre topologie

1. Sur un ordinateur exécutant Skype Entreprise Server ou sur lequel les outils d’administration Skype Entreprise Server sont installés, connectez-vous à l’aide d’un compte membre du groupe Utilisateurs local (ou d’un compte avec des droits d’utilisateur équivalents).
    
2. Démarrez le Générateur de topologie.
    
3. Dans l’arborescence de la console, accédez au pool frontal dans lequel vous souhaitez déployer l’archivage, puis cliquez sur le nom du pool frontal où vous souhaitez déployer l’archivage.
    
4. Dans le menu **Action**, cliquez sur **Modifier les propriétés**. 
    
5. Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur **Général**.
    
6. Faites défiler la liste jusqu’à **Archivage**.
    
7. Activez la case à cocher **Archivage**.
    
8. Sous **Archiver SQL Server store,** faites l’une des opérations suivantes :
    
   - Pour utiliser un magasin SQL Server existant, dans la zone de liste déroulante, cliquez sur le nom du magasin SQL Server que vous voulez utiliser. Si tous vos utilisateurs sont Microsoft Exchange Server 2013 ou supérieur, vous pouvez archiver les communications Skype Entreprise pour tous vos utilisateurs dans Exchange. Dans ce cas, vous n’avez pas besoin de configurer le SQL Server’archivage.
    
   - Pour spécifier une nouvelle SQL Server, cliquez sur **Nouveau,** puis dans la boîte de dialogue Définir un nouveau SQL Server **Store,** faites les choses suivantes :
    
   - Dans **SQL Server FQDN**, spécifiez le nom de SQL Server serveur sur lequel vous souhaitez créer le nouveau magasin.
    
   - Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou, pour définir une instance différente, cliquez sur **Instance nommée** et spécifiez l’instance à utiliser.
    
   - Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, sélectionnez la case à cocher Cette **instance SQL se** trouve dans la relation de mise en miroir, puis, dans le numéro de **port** Miroir, spécifiez le numéro de port.
    
9. Si vous souhaitez utiliser la mise en miroir SQL Server store, sélectionnez Activer SQL Server mise en miroir du **Store,** puis faites les choses suivantes :
    
   - Pour utiliser un magasin SQL Server existant pour la  mise en miroir, dans la zone de liste de listes de listes SQL Server miroir du magasin d’archivage, cliquez sur le nom du magasin SQL Server que vous souhaitez utiliser pour la mise en miroir.
    
   - Pour spécifier un nouveau magasin SQL Server pour la mise en miroir, cliquez sur **Nouveau,** puis dans la boîte de dialogue Définir un nouveau magasin **SQL Server,** faites l’une des choses suivantes :
    
     a. Dans **SQL Server FQDN**, spécifiez le FQDN du SQL Server sur lequel vous souhaitez créer le nouveau magasin SQL Server de données.
    
     b. Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser.
    
     c. Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, sélectionnez la case à cocher Cette **instance SQL se** trouve dans la relation de mise en miroir, puis, dans le numéro de **port** Miroir, spécifiez le numéro de port.
    
   - Si vous activez la mise en miroir SQL Server et que vous souhaitez inclure un témoin de mise en miroir SQL Server (une troisième instance de SQL Server distincte qui peut détecter l’état d’SQL Server principal et des instances miroir), sélectionnez le témoin de mise en miroir Utiliser **SQL Server** pour activer la case à cocher deover automatique, puis faites l’une des choses suivantes :
    
     a. Dans **SQL Server FQDN**, spécifiez le nom de groupe du serveur sur lequel vous souhaitez créer le témoin de mise en SQL Server de données.
    
     b. Cliquez sur **Instance par défaut** pour utiliser l’instance par défaut ou sur **Instance nommée** pour définir une instance différente, puis spécifiez l’instance à utiliser comme témoin de mise en miroir.
    
     c. Si l’instance SQL Server spécifiée se trouve dans une relation de mise en miroir, sélectionnez la case à cocher Cette **instance SQL se** trouve dans la relation de mise en miroir, puis, dans le numéro de **port** Miroir, spécifiez le numéro de port.
    
10. Pour enregistrer la configuration, cliquez sur **OK**.
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>Publier la topologie mise à jour pour ajouter une base de données d’archivage à votre déploiement

1. Sur un ordinateur qui exécute Skype Entreprise Server ou sur lequel les outils d’administration Skype Entreprise Server sont installés, connectez-vous à l’aide d’un compte membre du groupe Utilisateurs local (ou d’un compte avec des droits d’utilisateur équivalents).
    
    > [!NOTE]
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe Utilisateurs local, mais pour publier une topologie, qui est requis pour ajouter un serveur à la topologie, vous devez utiliser un compte membre du groupe **Administrateurs** du domaine et du groupe **RTCUniversalServerAdmins,** qui dispose d’autorisations de contrôle total (lecture, écriture et modification) sur le partage de fichiers que vous utilisez pour le magasin de fichiers Skype Entreprise Server (afin que le Générateur de topologie puisse configurer la liste de contrôle d’accès discrétionnaire requise ou un compte avec des droits équivalents).
  
2. Ouvrez la topologie que vous avez créée dans la section précédente à l’aide du Générateur de topologies.
    
3. Dans l’arborescence de la console, cliquez avec le bouton droit sur **Skype Entreprise Server,** puis cliquez sur **Publier la topologie.**
    
4. Dans la page **Publier la topologie**, cliquez sur **Suivant**.
    
5. Dans la page **Créer des bases de données**, vérifiez que la base de données est sélectionnée, puis cliquez sur **Suivant**. 
    
    > [!NOTE]
    > Si vous ne disposez pas des autorisations appropriées pour créer des bases de données, vous pouvez annuler la sélection de la base de données et laisser une autre personne dotée des autorisations nécessaires la créer. > seules les bases de données sur des serveurs SQL dédiés peuvent être installées à l’aide du Générateur de topologies. Les bases de données situées sur des serveurs SQL Server colocalisés avec d’autres composants serveur doivent être installées via une installation locale sur l’ordinateur concerné. 
  
6. Sur la page **Assistant Publication terminé**, assurez-vous que la topologie a été publiée comme il se doit, puis cliquez sur **Terminer**.
    
    > [!IMPORTANT]
    > Une fois la topologie publiée, vous devez configurer les options et les stratégies relatives à l’archivage pour permettre l’archivage du contenu. Pour plus d’informations, voir [Configure archiving options for Skype for Business Server](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server](configure-archiving-policies.md). 
  

