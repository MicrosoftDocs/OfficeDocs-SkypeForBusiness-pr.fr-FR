---
title: 'Déploiement d’un magasin de contacts unifié dans Skype entreprise Server '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Résumé : activez le magasin de contacts unifié dans Skype entreprise Server.'
ms.openlocfilehash: 382b4ed059c4066ae862bb3fe24b98b4bdde2a18
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798091"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>Déploiement d’un magasin de contacts unifié dans Skype entreprise Server
 
**Résumé :** Activez le magasin de contacts unifié dans Skype entreprise Server.
  
L’activation d’un magasin de contacts unifié dans Skype entreprise Server n’exige aucun paramètre de topologie. Pour activer le magasin de contacts unifié pour les utilisateurs :
  
- La stratégie du magasin de contacts unifié est activée (par défaut).
    
- Les utilisateurs se connectent à Skype entreprise au moins une fois.
    
Après la migration des contacts d’un utilisateur, ce qui se produit automatiquement lorsqu’un utilisateur se connecte à l’aide de Skype entreprise, l’utilisateur peut accéder à ses contacts Skype entreprise et les gérer depuis Skype entreprise, Outlook 2013 ou Outlook Web Access. Il n’est pas nécessaire de se connecter à Skype entreprise pour gérer ses contacts à partir d’Outlook ou d’Outlook Web Access.
  
> [!IMPORTANT]
> Si un utilisateur se connecte à partir de Skype entreprise après la migration, les contacts et les groupes sont disponibles et à jour, mais l’utilisateur ne peut pas gérer (c’est-à-dire ajouter, supprimer, déplacer, Baliser, supprimer ou modifier) ces contacts. 
  
## <a name="enable-users-for-unified-contact-store"></a>Activation des utilisateurs pour le magasin de contacts unifié

Lorsque vous déployez Skype entreprise Server et que vous publiez la topologie, le magasin de contacts unifié est activé par défaut pour tous les utilisateurs. Vous n’avez pas besoin d’effectuer d’action supplémentaire pour activer le magasin de contacts unifié après le déploiement de Skype entreprise Server. Cependant, vous pouvez utiliser l’applet de commande **Set-CsUserServicesPolicy** pour personnaliser les utilisateurs pour lesquels le magasin de contact unifié est disponible. Vous pouvez activer cette fonctionnalité globalement, par site, par locataire, par personne ou par groupes de personnes.
  
### <a name="to-enable-users-for-unified-contact-store"></a>Pour activer les utilisateurs pour le magasin de contact unifié

1. Démarrer Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
2. Effectuez l’une des opérations suivantes :
    
   - Pour activer globalement le magasin de contacts unifié pour tous les utilisateurs de Skype entreprise Server, procédez de l’une des manières suivantes dans l’interface de ligne de commande Windows PowerShell :
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - Pour activer le magasin de contact unifié pour tous les utilisateurs d’un site spécifique, à l’invite, tapez :
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   Par exemple :
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - Pour activer le magasin de contact unifié par locataire, à l’invite, tapez :
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   Exemple :
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - Pour activer le magasin de contact unifié pour des utilisateurs spécifiques, à l’invite, tapez :
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > Vous pouvez également utiliser un alias utilisateur ou un URI SIP à la place du nom d’affichage de l’utilisateur. 
  
    Exemple :
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > Dans l’exemple précédant, la première commande crée une nouvelle stratégie par utilisateur appelée Utilisateurs UCS activés avec l’indicateur UcsAllowed défini à True. La seconde commande affecte la stratégie à l’utilisateur avec le nom complet Ken Myer, ce qui signifie que Ken Myer est désormais activé pour le magasin de contact unifié.
  
## <a name="migrate-users-to-unified-contact-store"></a>Migration des utilisateurs vers le magasin de contacts unifié

Les contacts d’un utilisateur sont automatiquement déplacés vers le serveur Exchange 2013 lorsque l’utilisateur :
  
- une stratégie de services utilisateur dont le paramètre UcsAllowed a la valeur True a été attribuée à l’utilisateur ;
    
- A été configuré avec une boîte aux lettres Exchange 2013 et s’est connecté à la boîte aux lettres au moins une fois.
    
- Se connecte à l’aide d’un client enrichi Skype entreprise.
    
Si l’utilisateur se connecte avec un client Lync ou antérieur, ou si l’utilisateur n’est pas connecté à un serveur Exchange 2013, la stratégie de services des utilisateurs est ignorée et les contacts de l’utilisateur sont conservés dans Skype entreprise Server.
  
Déterminez si les contacts d’un utilisateur ont été transférés en utilisant l’une des méthodes suivantes : 
  
- Vérifiez la clé de Registre suivante sur l’ordinateur client :
    
    HKEY_CURRENT_USER \Software\Microsoft\Office\15.0\Lync\\<URL\>SIP \UCS
    
    Si les contacts de l’utilisateur sont stockés dans Exchange 2013, cette clé contient une valeur de InUCSMode avec une valeur de 2165.
    
- Exécutez l’applet de commande **Test-CsUnifiedContactStore**. Dans la ligne de commande de Skype entreprise Server Management Shell, tapez :
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    Si l’exécution de la commande **Test-CsUnifiedContactStore** s’est déroulée correctement, les contacts de l’utilisateur ont été migrés vers le magasin de contacts unifié.
    
## <a name="roll-back-migrated-users"></a>Restauration des utilisateurs migrés

Si vous avez besoin de restaurer la fonctionnalité de magasin de contacts unifiée, restaurez les contacts uniquement si vous revenez à l’utilisateur dans Exchange 2010 ou Lync Server 2010. Pour effectuer la restauration, désactivez la stratégie définie pour l’utilisateur, puis exécutez l’applet de commande **Invoke-CsUcsRollback**. La simple exécution de **Invoke-CsUcsRollback** ne suffit pas à garantir une restauration permanente ; en effet, si la stratégie n’est pas désactivée, le magasin de contacts unifié continue d’être transféré. Par exemple, si un utilisateur est restauré, car Exchange 2013 est restauré dans Exchange 2010, puis la boîte aux lettres de l’utilisateur est déplacée vers Exchange 2013, la migration de magasin de contacts unifiée sera lancée à nouveau après le Rollback, tant que magasin de contacts unifié est toujours activée pour l’utilisateur dans la stratégie de services des utilisateurs.
  
L’applet de commande **Move-Csuser** restaure automatiquement le magasin de contacts de l’utilisateur à partir de Exchange 2013 vers Skype entreprise Server dans les situations suivantes :
  
- Lorsque les utilisateurs sont déplacés de Skype entreprise Server vers Microsoft Lync Server 2013 ou Lync Server 2010. 
    
- Lorsque les utilisateurs sont déplacés vers l’environnement croisé, par exemple lorsqu’un utilisateur est déplacé de Skype entreprise Online vers Skype entreprise Server en local, ou vice versa.
    
L’importation des données d’un magasin de contacts unifié à partir d’une base de données de sauvegarde peut endommager les données du magasin de contacts unifié et les données utilisateur si le mode de magasin de contacts unifié a été modifié entre l’exportation et l’importation. Par exemple :
  
- Si vous exportez des listes de contacts avant la migration des contacts de l’utilisateur vers Exchange 2013, puis après la migration, vous importez les mêmes données, les données et les listes de contacts du magasin de contacts unifié seront corrompues.
    
- Si vous exportez les données des utilisateurs après avoir migré les utilisateurs vers Exchange 2013, restaurez la migration, puis, pour une raison quelconque, vous importez les données à partir de la migration, les données et les listes de contacts du magasin de contacts unifié seront endommagées.
    
> [!IMPORTANT]
> Avant de déplacer une boîte aux lettres Exchange à partir d’Exchange 2013 vers Exchange 2010, l’administrateur Exchange doit s’assurer que l’administrateur de Skype entreprise Server a préalablement restauré les contacts de l’utilisateur de Skype entreprise à partir d’Exchange 2013 vers Skype pour Business Server. Pour restaurer des contacts de magasin de contacts unifiés dans Skype entreprise Server, reportez-vous à la procédure « pour restaurer des contacts de magasin de contacts unifiés à partir d’Exchange 2013 vers Skype entreprise Server » plus loin dans cette section. 
  
 **Pour restaurer des contacts de l’utilisateur, procédez comme suit :** Si vous utilisez l’applet de action **Move-Csuser** pour déplacer des utilisateurs entre Skype entreprise Server 2015 et Lync Server 2010, vous pouvez ignorer ces étapes dans la mesure où l’applet de **passe de migration-Csuser** a restauré automatiquement le magasin de contacts unifié lorsque le déplacement des utilisateurs de Skype entreprise Server 2015 vers Lync Server 2010. La migration **-Csuser** n’entraîne pas la désactivation de la stratégie de magasin de contacts unifiée, de sorte que la migration vers le magasin de contacts unifié se reproduit si l’utilisateur est reculé dans Skype entreprise Server 2015.
  

