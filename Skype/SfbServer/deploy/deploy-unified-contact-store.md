---
title: 'Déployer le magasin de contacts unifié dans Skype pour Business Server '
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Résumé : Activer le magasin de contacts unifié dans Skype pour Business Server.'
ms.openlocfilehash: 36515e9542a18d422254292b0cf2a2b4ef937178
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20978220"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>Déployer le magasin de contacts unifié dans Skype pour Business Server
 
**Résumé :** Activer le magasin de contacts unifié dans Skype pour Business Server.
  
Activation du magasin de contacts unifié dans Skype pour Business Server ne nécessite pas les paramètres de la topologie. Pour activer le magasin de contacts unifié pour les utilisateurs :
  
- La stratégie du magasin de contacts unifié est activée (par défaut).
    
- Les utilisateurs se connectent avec Skype pour les entreprises au moins une fois.
    
Une fois que les contacts d’un utilisateur ont été migrés, ce qui se produit automatiquement lorsqu’un utilisateur se connecte avec Skype pour les entreprises, l’utilisateur peut accéder et gérer leur Skype de contacts professionnels à partir de Skype pour les professionnels, Outlook 2013 ou Outlook Web Access. L’utilisateur n’a pas à être connecté à Skype pour les entreprises à gérer leurs contacts dans Outlook ou Outlook Web Access.
  
> [!IMPORTANT]
> Si un utilisateur se connecte en Skype pour les entreprises après la migration, les contacts et les groupes sont disponibles et à jour, mais l’utilisateur ne peut pas gérer (qui est, ajouter, supprimer, déplacer, tag, baliser ou modifier) ces contacts. 
  
## <a name="enable-users-for-unified-contact-store"></a>Activation des utilisateurs pour le magasin de contacts unifié

Lorsque vous déployez Skype pour Business Server et que vous publiez la topologie, le magasin de contacts unifié est activé pour tous les utilisateurs par défaut. Il est inutile d’aucune action supplémentaire pour activer le magasin de contacts unifié après avoir déployé Skype pour Business Server. Toutefois, vous pouvez utiliser l’applet de commande **Set-CsUserServicesPolicy** pour personnaliser les utilisateurs qui ont unifiés magasin de contacts. Vous pouvez activer cette fonctionnalité globalement, par site, par locataire, par personne ou par groupes de personnes.
  
### <a name="to-enable-users-for-unified-contact-store"></a>Pour activer les utilisateurs pour le magasin de contact unifié

1. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour les entreprises**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
2. Effectuez l’une des opérations suivantes :
    
   - Pour activer le magasin de contacts unifié globalement pour tous les Skype pour les utilisateurs Business Server, notamment l’applet de commande suivante à l’interface de ligne de commande Windows PowerShell :
    
   ```
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - Pour activer le magasin de contact unifié pour tous les utilisateurs d’un site spécifique, à l’invite, tapez :
    
   ```
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   Exemple :
    
   ```
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - Pour activer le magasin de contact unifié par locataire, à l’invite, tapez :
    
   ```
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   Exemple :
    
   ```
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - Pour activer le magasin de contact unifié pour des utilisateurs spécifiques, à l’invite, tapez :
    
   ```
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > Vous pouvez également utiliser un alias utilisateur ou un URI SIP à la place du nom d’affichage de l’utilisateur. 
  
    Exemple :
    
   ```
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > Dans l’exemple précédant, la première commande crée une nouvelle stratégie par utilisateur appelée Utilisateurs UCS activés avec l’indicateur UcsAllowed défini à True. La seconde commande affecte la stratégie à l’utilisateur avec le nom complet Ken Myer, ce qui signifie que Ken Myer est désormais activé pour le magasin de contact unifié.
  
## <a name="migrate-users-to-unified-contact-store"></a>Migration des utilisateurs vers le magasin de contacts unifié

Contacts d’un utilisateur sont transférés automatiquement vers le serveur Exchange 2013 lorsque l’utilisateur :
  
- une stratégie de services utilisateur dont le paramètre UcsAllowed a la valeur True a été attribuée à l’utilisateur ;
    
- A été mis en service avec une boîte aux lettres Exchange 2013 et s’est connecté à la boîte aux lettres au moins une fois.
    
- Journaux dans à l’aide d’un Skype pour le client riche Business.
    
Si l’utilisateur se connecte avec un client antérieure ou de Lync, ou si l’utilisateur n’est pas connecté à un serveur Exchange 2013, la stratégie de services utilisateur est ignorée et les contacts de l’utilisateur restent dans Skype pour Business Server.
  
Déterminez si les contacts d’un utilisateur ont été transférés en utilisant l’une des méthodes suivantes : 
  
- Vérifiez la clé de Registre suivante sur l’ordinateur client :
    
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\< URL SIP\>\UCS
    
    Si les contacts de l’utilisateur sont stockés dans Exchange 2013, cette clé contient une valeur inucsmode dont la valeur est 2165.
    
- Exécutez l’applet de commande **Test-CsUnifiedContactStore** . À Skype pour la ligne de commande Business Server Management Shell, tapez :
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    Si le **Test-CsUnifiedContactStore** réussit, les contacts de l’utilisateur ont été migrés vers le magasin de contacts unifié.
    
## <a name="roll-back-migrated-users"></a>Restauration des utilisateurs migrés

Si vous avez besoin restaurer le contact unifié magasin fonctionnalité, annuler les contacts uniquement si vous déplacez l’utilisateur vers Exchange 2010 ou Lync Server 2010. Pour annuler, désactivez la stratégie de l’utilisateur, puis exécutez l’applet de commande **Invoke-csucsrollback ne** . **Invoke-csucsrollback ne** décrire l’exécution n’est pas suffisant pour assurer la restauration définitive, étant donné que le magasin de contacts unifié migration sera effectuée à nouveau si la stratégie n’est pas désactivée. Par exemple, si un utilisateur est annulé, car Exchange 2013 est restaurée vers Exchange 2010, puis la boîte aux lettres est déplacée vers Exchange 2013, la migration de magasin de contacts unifié sera effectuée à nouveau sept jours après la restauration, dans la mesure où stocker de contact unifié est toujours activé pour l’utilisateur dans la stratégie de services utilisateur.
  
L’applet de commande **Move-CsUser** restaure automatiquement magasin de contacts de l’utilisateur à partir d’Exchange 2013 à Skype pour Business Server dans les situations suivantes :
  
- Lorsque les utilisateurs sont déplacés de Skype pour Business Server vers Lync Server 2010 ou de Microsoft Lync Server 2013. 
    
- Lorsque les utilisateurs sont transférés local, par exemple lorsqu’un utilisateur est déplacé de Skype pour Business Online à Skype pour Business Server local, ou vice versa.
    
L’importation des données d’un magasin de contacts unifié à partir d’une base de données de sauvegarde peut endommager les données du magasin de contacts unifié et les données utilisateur si le mode de magasin de contacts unifié a été modifié entre l’exportation et l’importation. Par exemple :
  
- Si vous exportez des listes de contacts avant de contacts des utilisateurs sont migrés vers Exchange 2013 et, après la migration, vous importerez les mêmes données, les données de magasin de contacts unifié et les listes de contacts seront endommagées.
    
- Si vous exportez des données utilisateur après la migration des utilisateurs vers Exchange 2013, annuler la migration, puis pour une raison quelconque, vous importez les données d’après la migration, le contact unifié stockent des données et listes de contacts seront endommagées.
    
> [!IMPORTANT]
> Avant de déplacer une boîte aux lettres Exchange vers Exchange 2010 à partir d’Exchange 2013, l’administrateur Exchange devez vous assurer que le Skype pour l’administrateur du serveur d’entreprise a tout d’abord restaurée la Skype pour les contacts des utilisateurs Business Server à partir d’Exchange 2013 à Skype pour Serveur d’entreprise. Pour restaurer les contacts de magasin de contacts unifié Skype pour Business Server, consultez la procédure « pour restaurer les contacts du magasin de contacts unifié de Exchange 2013 à Skype pour Business Server » plus loin dans cette section. 
  
 **Comment restaurer les contacts de l’utilisateur :** Si vous utilisez l’applet de commande **Move-CsUser** pour déplacer des utilisateurs entre Skype pour Business Server 2015 et Lync Server 2010, vous pouvez ignorer ces étapes, car l’applet de commande **Move-CsUser** restaure automatiquement magasin de contacts unifié lorsqu’il déplace les utilisateurs de Skype pour Entreprise 2015 serveur Lync Server 2010. **Move-CsUser** ne désactive pas la stratégie du magasin de contacts unifié, afin que la migration vers le magasin de contacts unifié se reproduit si l’utilisateur est déplacé vers Skype pour Business Server 2015.
  

