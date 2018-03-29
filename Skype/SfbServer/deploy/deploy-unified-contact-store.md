---
title: Déployer le magasin de contacts unifié dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Résumé : Activer le magasin de contacts unifié dans Skype pour Business Server 2015.'
ms.openlocfilehash: fbe94023a6693f7d016d2963d49d88646c9b969e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server-2015"></a>Déployer le magasin de contacts unifié dans Skype Entreprise Server 2015
 
**Résumé :** Activer le magasin de contacts unifié dans Skype pour Business Server 2015.
  
L’activation du magasin de contacts unifiée dans Skype pour Business Server 2015 ne nécessite pas de tous les paramètres de topologie. Pour activer le magasin de contacts unifié pour les utilisateurs :
  
- La stratégie du magasin de contacts unifié est activée (par défaut).
    
- Les utilisateurs se connectent avec Skype pour entreprise au moins une fois.
    
Une fois les contacts d’un utilisateur, qui se produit automatiquement lorsqu’un utilisateur se connecte avec Skype pour les entreprises, ont été migrés, l’utilisateur peut accéder et gérer leur Skype pour les contacts professionnels à partir de Skype pour Outlook Web Access, Outlook 2013 ou entreprise. L’utilisateur n’a pas à être connecté à Skype pour les entreprises à gérer leurs contacts depuis Outlook ou Outlook Web Access.
  
> [!IMPORTANT]
> Si un utilisateur se connecte depuis Skype pour entreprise après la migration, les contacts et les groupes sont disponibles et à jour, mais l’utilisateur ne peut pas gérer (qui est, ajouter, supprimer, déplacer, balise, baliser ou modifier) les contacts. 
  
## <a name="enable-users-for-unified-contact-store"></a>Activation des utilisateurs pour le magasin de contacts unifié

Lorsque vous déployez Skype pour Business Server 2015 et que vous publiez la topologie, le magasin de contacts unifiée est activée pour tous les utilisateurs par défaut. Vous n’avez pas besoin de toute action supplémentaire pour activer le magasin de contacts unifiée après avoir déployé Skype pour Business Server 2015. Toutefois, vous pouvez utiliser l’applet de commande **Set-CsUserServicesPolicy** pour personnaliser les utilisateurs qui ont unifiés magasin de contacts. Vous pouvez activer cette fonctionnalité globalement, par site, par locataire, par personne ou par groupes de personnes.
  
### <a name="to-enable-users-for-unified-contact-store"></a>Pour activer les utilisateurs pour le magasin de contact unifié

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Effectuez l’une des opérations suivantes :
    
   - Pour activer le magasin de contacts unifiée globalement pour tous les Skype pour les utilisateurs du serveur de l’entreprise, notamment l’applet de commande suivante à l’interface de ligne de commande de Windows PowerShell :
    
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
    > Dans l’exemple précédent, la première commande crée une nouvelle stratégie par utilisateur nommée utilisateurs UCS avec l’indicateur UcsAllowed défini sur True. La seconde commande affecte la stratégie à l’utilisateur avec le nom complet Ken Myer, ce qui signifie que Ken Myer est désormais activé pour le magasin de contact unifié.
  
## <a name="migrate-users-to-unified-contact-store"></a>Migration des utilisateurs vers le magasin de contacts unifié

Les contacts d’un utilisateur sont automatiquement migrés vers le serveur Exchange 2013 lorsque l’utilisateur :
  
- une stratégie de services utilisateur dont le paramètre UcsAllowed a la valeur True a été attribuée à l’utilisateur ;
    
- A été configuré avec une boîte aux lettres Exchange 2013 et s’est connecté à la boîte aux lettres au moins une fois.
    
- Journaux dans à l’aide d’un Skype pour client riche d’entreprise.
    
Si l’utilisateur se connecte avec un Lync client ou antérieur, ou si l’utilisateur n’est pas connecté à un serveur Exchange 2013, la stratégie des services utilisateur est ignorée et les contacts de l’utilisateur restent dans Skype pour Business Server.
  
Déterminez si les contacts d’un utilisateur ont été transférés en utilisant l’une des méthodes suivantes : 
  
- Vérifiez la clé de Registre suivante sur l’ordinateur client :
    
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\< URL du SIP\>\UCS
    
    Si les contacts de l’utilisateur sont stockées dans Exchange 2013, cette clé contient une valeur de InUCSMode avec une valeur de 2165.
    
- Exécutez l’applet de commande **Test-CsUnifiedContactStore** . À la Skype pour Business Server Management Shell de ligne de commande, tapez :
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    Si **CsUnifiedContactStore-Test** réussit, les contacts de l’utilisateur ont été migrés vers le magasin de contacts unifiée.
    
## <a name="roll-back-migrated-users"></a>Restauration des utilisateurs migrés

Si vous devez restaurer le contact unifié fonctionnalité de stocker, restaurer les contacts que si vous déplacez l’utilisateur vers Exchange 2010 ou Microsoft Lync Server 2010. Pour annuler, désactivez la stratégie de l’utilisateur, puis exécuter l’applet de commande **Invoke-CsUcsRollback** . Exécution de **Invoke-CsUcsRollback** seul n’est pas suffisant pour assurer la restauration permanente, parce que le magasin de contacts unifiée migration sera lancée à nouveau si la stratégie n’est pas désactivée. Par exemple, si un utilisateur est annulé, car Exchange 2013 est restaurée vers Exchange 2010, et ensuite les boîtes aux lettres de l’utilisateur est déplacé vers Exchange 2013, la migration du magasin de contacts unifiée sera lancée à nouveau sept jours après la restauration, dans la mesure où stocker les contacts unifiée est toujours activée pour l’utilisateur dans la stratégie des services utilisateur.
  
L’applet de commande **Move-CsUser** annule automatiquement magasin de contacts de l’utilisateur à partir d’Exchange 2013 à Skype pour Business Server 2015 dans les situations suivantes :
  
- Lorsque les utilisateurs passent de Skype pour 2015 de serveur d’entreprise de Microsoft Lync Server 2013 ou Lync Server 2010. 
    
- Lorsque les utilisateurs sont migrés entre des locaux, par exemple lorsqu’un utilisateur est déplacé de Skype pour Business Online à Skype pour Business Server 2015 sur site, ou vice versa.
    
L’importation des données d’un magasin de contacts unifié à partir d’une base de données de sauvegarde peut endommager les données du magasin de contacts unifié et les données utilisateur si le mode de magasin de contacts unifié a été modifié entre l’exportation et l’importation. Par exemple :
  
- Si vous exportez des listes de contacts avant de contacts des utilisateurs sont migrés vers Exchange 2013 et, après la migration, vous importerez les mêmes données, les données du magasin de contacts unifiée et les listes de contacts seront endommagées.
    
- Si vous exportez des données de l’utilisateur après avoir migré des utilisateurs vers Exchange 2013, restaurer la migration et puis pour une raison quelconque, vous importez les données d’après la migration, le contact unifié stocker des données et des listes de contact seront endommagées.
    
> [!IMPORTANT]
> Avant de déplacer une boîte aux lettres Exchange à partir d’Exchange 2013 pour Exchange 2010, l’administrateur Exchange doit Assurez-vous que le Skype pour l’administrateur du serveur de l’entreprise a tout d’abord restaurée la Skype pour les contacts des utilisateurs Business Server à partir d’Exchange 2013 à Skype pour Serveur d’entreprise. Pour restaurer les contacts unifiée magasin de contacts Skype pour Business Server, voir la procédure « pour restaurer contacts du magasin de contacts unifiée de Exchange 2013 à Skype pour Business Server » plus loin dans cette section. 
  
 **Comment restaurer des contacts de l’utilisateur :** Si vous utilisez l’applet de commande **Move-CsUser** pour déplacer des utilisateurs entre Skype pour Business Server 2015 et Lync Server 2010, vous pouvez ignorer ces étapes car l’applet de commande **Move-CsUser** annule automatiquement magasin de contacts unifiée lorsqu’il déplace d’utilisateurs de Skype pour Entreprise 2015 de serveur Lync Server 2010. **Move-CsUser** ne désactive pas la stratégie du magasin de contacts unifiée, afin que la migration vers le magasin de contacts unifiée se reproduira si l’utilisateur est déplacé vers Skype pour Business Server 2015.
  

