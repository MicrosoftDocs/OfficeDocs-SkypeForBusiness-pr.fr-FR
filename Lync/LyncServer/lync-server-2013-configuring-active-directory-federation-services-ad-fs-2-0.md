---
title: Configuration d’Active Directory Federation Services (AD FS 2.0)
TOCTitle: Configuration d’Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn308561(v=OCS.15)
ms:contentKeyID: 56269560
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration d’Active Directory Federation Services (AD FS 2.0)

 

_**Dernière rubrique modifiée :** 2016-12-08_

Cette section décrit la configuration d’Active Directory Federation Services (AD FS 2.0) pour prendre en charge l’authentification multifacteur. Pour plus d’informations sur l’installation d’AD FS 2.0, voir les guides détaillés et procéduraux pour AD FS 2.0 accessibles via la page [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).

> [!NOTE]  
> Lorsque vous installez AD FS 2.0, vous ne devez pas utiliser le Gestionnaire de serveur Windows pour ajouter le rôle Active Directory Federation Services. À la place, vous devez télécharger et installer le package Active Directory Federation Services 2.0 RTW accessible via la page <a href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</a>.


**Pour configurer AD FS pour l’authentification à deux facteurs**

1.  Connectez-vous à l’ordinateur AD FS 2.0 à l’aide d’un compte d’administrateur de domaine.

2.  Démarrez Windows PowerShell.

3.  Depuis la ligne de commande Windows PowerShell, exécutez la commande suivante :
    
        add-pssnapin Microsoft.Adfs.PowerShell

4.  Établissez un partenariat avec chaque directeur, pool d’entreprise et serveur Standard Edition Lync Server 2013 avec les mises à jour cumulatives pour Lync Server 2013 de juillet 2013 pour lequel l’authentification passive sera activée en exécutant la commande suivante (remplacez le nom du serveur spécifique de votre déploiement) :
    
        Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  Dans le menu Outils d’administration, démarrez la console de gestion AD FS 2.0.

6.  Développez **Relations d’approbation** \> **Relations d’approbation de la partie de confiance**.

7.  Vérifiez qu’une relation de confiance a été créée pour votre pool d’entreprise ou serveur Standard Edition Lync Server 2013 avec les mises à jour cumulatives pour Lync Server 2013 de juillet 2013.

8.  Créez et affectez une règle d’autorisation d’émission pour votre relation d’approbation de la partie de confiance à l’aide de Windows PowerShell en exécutant les commandes suivantes :
    
    ```
    $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
    ```
    ```
    Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
    -IssuanceAuthorizationRules $IssuanceAuthorizationRules
    ```    

9.  Créez et affectez une règle de transformation d’émission pour votre relation d’approbation de la partie de confiance à l’aide de Windows PowerShell en exécutant les commandes suivantes :
    
    ```
    $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
    ```
    ```
    Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
    ```

10. Dans la console de gestion AD FS 2.0, cliquez avec le bouton droit sur votre relation d’approbation de la partie de confiance, puis sélectionnez **Modifier les règles de revendication**.

11. Sélectionnez l’onglet **Règles d’autorisation d’émission**, puis vérifiez que la règle d’autorisation a été correctement créée.

12. Sélectionnez l’onglet **Règles de transformation d’émission**, puis vérifiez que la règle de transformation d’émission a été correctement créée.

