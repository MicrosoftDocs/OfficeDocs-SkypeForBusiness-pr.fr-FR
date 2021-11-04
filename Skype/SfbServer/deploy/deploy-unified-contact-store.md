---
title: 'Déployer un magasin de contacts unifié dans Skype Entreprise Server '
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Résumé : Activez le magasin de contacts unifié dans Skype Entreprise Server.'
ms.openlocfilehash: 459626fe40f76cc19534aaff67d1b1b39c268469
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60748830"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>Déployer un magasin de contacts unifié dans Skype Entreprise Server
 
**Résumé :** Activez le magasin de contacts unifié dans Skype Entreprise Server.
  
L’activation du magasin de contacts unifié Skype Entreprise Server ne nécessite aucun paramètre de topologie. Pour activer le magasin de contacts unifié pour les utilisateurs :
  
- La stratégie du magasin de contacts unifié est activée (par défaut).
    
- Les utilisateurs se connectent Skype Entreprise au moins une fois.
    
Une fois les contacts d’un utilisateur migrés, ce qui se produit automatiquement lorsqu’un utilisateur se connecte avec Skype Entreprise, l’utilisateur peut accéder à ses contacts Skype Entreprise et les gérer à partir de Skype Entreprise, Outlook 2013 ou Outlook Web Access. L’utilisateur n’a pas besoin d’être connecté à Skype Entreprise pour gérer ses contacts depuis Outlook ou Outlook Web Access.
  
> [!IMPORTANT]
> Si un utilisateur se connecte à partir de Skype Entreprise après la migration, les contacts et les groupes sont disponibles et à jour, mais l’utilisateur ne peut pas gérer (c’est-à-dire, ajouter, supprimer, déplacer, baliser, supprimer ou modifier) ces contacts. 
  
## <a name="enable-users-for-unified-contact-store"></a>Activer les utilisateurs pour le magasin de contacts unifié

Lorsque vous déployez Skype Entreprise Server et publiez la topologie, le magasin de contacts unifié est activé par défaut pour tous les utilisateurs. Vous n’avez pas besoin d’action supplémentaire pour activer le magasin de contacts unifié après avoir déployé Skype Entreprise Server. Cependant, vous pouvez utiliser l’applet de commande **Set-CsUserServicesPolicy** pour personnaliser les utilisateurs pour lesquels le magasin de contact unifié est disponible. Vous pouvez activer cette fonctionnalité globalement, par site, par locataire, par personne ou par groupes de personnes.
  
### <a name="to-enable-users-for-unified-contact-store"></a>Pour activer les utilisateurs pour le magasin de contact unifié

1. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur Démarrer, sur Tous les **programmes,** sur **Skype Entreprise,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Effectuez l’une des opérations suivantes :
    
   - Pour activer le magasin de contacts unifié globalement pour tous les Skype Entreprise Server utilisateurs, inter-cmdlet suivante dans l’interface Windows PowerShell ligne de commande suivante :
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - Pour activer le magasin de contacts unifié pour les utilisateurs d’un site spécifique, à l’invite, tapez :
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   Par exemple :
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - Pour activer le magasin de contacts unifié par client, à l’invite, tapez :
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   Par exemple :
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - Pour activer le magasin de contacts unifié pour des utilisateurs spécifiques, à l’invite, tapez :
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > Vous pouvez également utiliser un alias utilisateur ou un URI SIP à la place du nom d’affichage de l’utilisateur. 
  
    Par exemple :
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > Dans l’exemple précédant, la première commande crée une nouvelle stratégie par utilisateur appelée Utilisateurs UCS activés avec l’indicateur UcsAllowed défini à True. La seconde commande affecte la stratégie à l’utilisateur avec le nom complet Ken Myer, ce qui signifie que Ken Myer est désormais activé pour le magasin de contact unifié.
  
## <a name="migrate-users-to-unified-contact-store"></a>Migrer des utilisateurs vers un magasin de contacts unifié

Les contacts d’un utilisateur sont transférés automatiquement vers le serveur Exchange 2013 quand :
  
- une stratégie de services utilisateur dont le paramètre UcsAllowed a la valeur True a été attribuée à l’utilisateur ;
    
- A été mis en service avec une boîte Exchange 2013 et s’y est déjà inscrit au moins une fois.
    
- l'utilisateur se connecte à l'aide d'un client riche Skype Entreprise.
    
Si l’utilisateur se connecte avec un client Lync ou un client précédent, ou s’il n’est pas connecté à un serveur Exchange 2013, la stratégie de services d’utilisateurs est ignorée et les contacts de l’utilisateur restent dans Skype Entreprise Server.
  
Déterminez si les contacts d’un utilisateur ont été transférés en utilisant l’une des méthodes suivantes : 
  
- Vérifiez la clé de Registre suivante sur l’ordinateur client :
    
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync<\\ URL SIP \> \UCS
    
    Si les contacts de l’utilisateur sont stockés dans Exchange 2013, cette clé contient la valeur InUCSMode avec la valeur 2165.
    
- Exécutez l’applet de commande **Test-CsUnifiedContactStore**. Sur la ligne de Skype Entreprise Server Management Shell, tapez :
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    Si l’exécution de la commande **Test-CsUnifiedContactStore** s’est déroulée correctement, les contacts de l’utilisateur ont été migrés vers le magasin de contacts unifié.
    
## <a name="roll-back-migrated-users"></a>Roll Back Migrated Users

Si vous avez besoin de la fonctionnalité de magasin de contacts unifié, revenir aux contacts uniquement si vous déplacez l’utilisateur vers Exchange 2010 ou Lync Server 2010. Pour effectuer la restauration, désactivez la stratégie définie pour l’utilisateur, puis exécutez l’applet de commande **Invoke-CsUcsRollback**. Le fait de simplement exécuter **Invoke-CsUcsRollback** ne suffit pas à garantir une restauration permanente ; en effet, si la stratégie n’est pas désactivée, le magasin de contacts unifié continuera d’être transféré. Par exemple, si un utilisateur est retourné parce que Exchange 2013 est revenir à Exchange 2010, puis que la boîte aux lettres de l’utilisateur est déplacée vers Exchange 2013, la migration du magasin de contacts unifié est initiée à nouveau sept jours après la mise à jour, tant que le magasin de contacts unifié est toujours activé pour l’utilisateur dans la stratégie de services d’utilisateurs.
  
L’cmdlet **Move-CsUser** retourne automatiquement le magasin de contacts de l’utilisateur de Exchange 2013 à Skype Entreprise Server dans les situations suivantes :
  
- Lorsque les utilisateurs sont déplacés Skype Entreprise Server vers Microsoft Lync Server 2013 ou Lync Server 2010. 
    
- Lorsque les utilisateurs sont migrés entre les locaux, par exemple lorsqu’un utilisateur est déplacé de Skype Entreprise Online vers Skype Entreprise Server local, ou inversement.
    
L’importation des données d’un magasin de contacts unifié à partir d’une base de données de sauvegarde peut endommager les données du magasin de contacts unifié et les données utilisateur si le mode de magasin de contacts unifié a été modifié entre l’exportation et l’importation. Par exemple :
  
- Si vous exportez des listes de contacts avant la migration des contacts des utilisateurs vers Exchange 2013, puis, après la migration, importez les mêmes données, les données du magasin de contacts unifié et les listes de contacts seront endommagées.
    
- Si vous exportez des données utilisateur après avoir migré des utilisateurs vers Exchange 2013, revenir en arrière de la migration, puis pour une raison quelconque vous importez les données après la migration, les données du magasin de contacts unifié et les listes de contacts seront endommagées.
    
> [!IMPORTANT]
> Avant de déplacer une boîte aux lettres Exchange de Exchange 2013 vers Exchange 2010, l’administrateur Exchange doit s’assurer que l’administrateur Skype Entreprise Server a d’abord retourné l’utilisateur Skype Entreprise Server de Exchange 2013 à Skype Entreprise Server. Pour revenir aux contacts du magasin de contacts unifié vers Skype Entreprise Server, consultez la procédure « Pour faire revenir les contacts du magasin de contacts unifié de Exchange 2013 à Skype Entreprise Server », plus loin dans cette section. 
  
 **Comment récupérer les contacts utilisateur :** Si vous utilisez l’cmdlet **Move-CsUser** pour déplacer des utilisateurs entre Skype Entreprise Server 2015 et Lync Server 2010, vous pouvez ignorer ces étapes, car l’cmdlet **Move-CsUser** permet de revenir automatiquement au magasin de contacts unifié lorsqu’elle déplace les utilisateurs de Skype Entreprise Server 2015 vers Lync Server 2010. **Move-CsUser** ne désactive pas la stratégie de magasin de contacts unifié, de sorte que la migration vers le magasin de contacts unifié se reproduira si l’utilisateur est revenir à Skype Entreprise Server 2015.
  

