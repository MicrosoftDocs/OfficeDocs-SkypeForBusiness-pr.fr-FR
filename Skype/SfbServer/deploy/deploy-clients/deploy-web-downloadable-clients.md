---
title: Déploiement des clients web téléchargeables pour Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Résumé : Déployer le Skype pour Business Web App et application de réunions Skype utilisé avec Skype pour les entreprises.'
ms.openlocfilehash: e1cee2741e1538da1e4c5ed8e25509415cb16ac3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server-2015"></a>Déploiement des clients web téléchargeables pour Skype Entreprise Server 2015
 
**Résumé :** Déployer le Skype pour Business Web App et application de réunions Skype utilisé avec Skype pour les entreprises.
  
Skype pour Business Web App est un client web Internet Information Services (IIS) est installé sur le serveur exécutant Skype pour Business Server 2015 et par défaut qu'il est déployé sur demande aux utilisateurs de réunion qui n’ont pas déjà la Skype pour client d’entreprise. Ces utilisateurs de réunion sont le plus souvent que ne pas connexion à partir de l’extérieur de votre réseau. Chaque fois qu’un utilisateur clique sur une URL de la réunion, mais n’a pas le Skype pour client d’entreprise installé, l’utilisateur est présenté avec l’option pour joindre la réunion à l’aide de la dernière version de Skype pour Business Web App.
  
La voix, vidéo et partage les fonctionnalités dans Skype pour Business Web App nécessitent un contrôle Microsoft ActiveX qui est utilisé comme un plug-in par le navigateur de l’utilisateur. Vous pouvez installer le contrôle ActiveX à l’avance ou permettre aux utilisateurs d’installer lorsque vous y êtes invité, ce qui se passe la première fois qu’ils utilisent Skype pour Business Web App ou la première fois qu’ils accèdent à une fonction qui requiert le contrôle ActiveX.
  
> [!NOTE]
> Dans Skype pour les déploiements de serveur de transport Edge 2015 Business Server, un serveur proxy inverse HTTPS dans le réseau de périmètre est requis pour Skype pour l’accès client Business Web App. Vous devez également publier des URL simples. Pour plus d’informations, consultez [Configuration des serveurs Proxy inverse](http://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) et [planification d’URL Simple](http://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx). 
  
## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Activer l’authentification à plusieurs facteurs pour Skype pour Business Web App
<a name="MFA"> </a>

Le Skype pour la version Business Server 2015 de Skype pour Business Web App prend en charge l’authentification à plusieurs facteurs. Outre le nom d’utilisateur et le mot de passe, vous pouvez exiger des méthodes d’authentification supplémentaires, tels que des cartes à puce ou de broches, à authentifier les utilisateurs qui appartiennent à partir de réseaux externes lors de leur inscription à Skype pour les réunions d’entreprise. Vous pouvez activer l’authentification à facteurs multiples par un déploiement de serveur de fédération de Service de fédération Active Directory (Active Directory Federation Services) et l’activation de l’authentification de passive dans Skype pour Business Server 2015. Après avoir configuré ADFS, les utilisateurs externes qui tentent de joindre Skype pour les réunions d’entreprise sont présentées avec une page Web une authentification multifacteur AD FS qui contient le nom d’utilisateur et défi de mot de passe en même temps que les autres méthodes d’authentification que vous avez avez configuré.
  
> [!IMPORTANT]
> Vous trouverez ci-dessous des considérations importantes si vous envisagez de configurer les services AD FS pour l’authentification multifacteur : 
  
- L'authentification ADFS multifacteur fonctionne si le participant à la réunion et l'organisateur appartiennent à la même organisation ou à une organisation fédérée AD FS. Elle ne fonctionne pas pour les utilisateurs fédérés Lync, car l’infrastructure web du serveur Lync ne la prend pas en charge pour le moment.
    
- Si vous utilisez des équilibreurs de charge matériels, activer la persistance de cookie sur les équilibreurs de charge afin que toutes les demandes provenant du Skype pour client d’entreprise Web App sont traitées par le même serveur frontal.
    
- Lorsque vous établissez une approbation de tiers de confiance entre Skype pour serveurs Business Server et d’AD FS, affecter une durée de vie de jeton est suffisamment longue pour couvrir la longueur maximale de votre Skype pour les réunions d’entreprise. Une durée de vie de jeton de 240 minutes est généralement suffisante.
    
- Cette configuration ne s’applique pas aux clients mobiles Lync.
    
### <a name="configure-multi-factor-authentication"></a>Configuration de l'authentification multifacteur

1. Installez un rôle de serveur de fédération AD FS. Pour plus d’informations, consultez le [Guide de déploiement de Active Directory Federation Services 2.0](https://go.microsoft.com/fwlink/p/?linkid=267511)
    
2. Créez des certificats pour AD FS. Pour plus d’informations, consultez la section [« Certificats de serveur de fédération »](https://go.microsoft.com/fwlink/p/?LinkId=285376) du Plan et déployer ADFS pour une utilisation avec une seule ouverture de session de la rubrique.
    
3. À partir de l’interface de ligne de commande de Windows PowerShell, exécutez la commande suivante :
    
    ```
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. Établissez un partenariat en exécutant la commande suivante :
    
    ```
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. Définissez les règles de partie de confiance suivantes :
    
    ```
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   ```
 
   ```
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   ```

   ```
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>Désactivation de BranchCache 
<a name="MFA"> </a>

La fonctionnalité BranchCache dans Windows 7 et Windows Server 2008 R2 peut interférer avec Skype pour les composants web Business Web App. Pour éviter les problèmes de Skype pour les utilisateurs d’entreprise Web App, assurez-vous que BranchCache n’est pas activé. 
  
Pour plus d’informations sur la désactivation de BranchCache, consultez le Guide de déploiement de BranchCache, qui est disponible dans le format Word à Microsoft Download Center au [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?LinkId=268788) et au format HTML dans la bibliothèque Windows Server 2008 R2 technique à [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?LinkId=268789).
  
## <a name="verifying-skype-for-business-web-app-deployment"></a>Vérification de Skype pour le déploiement d’applications métier Web
<a name="MFA"> </a>

Vous pouvez utiliser l'applet de commande Test-CsUcwaConference pour vérifier que deux utilisateurs de test peuvent participer à une conférence à l'aide de l'API UCWA (Unified Communications Web API). Pour plus d’informations sur cette applet de commande, reportez-vous à la section [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) dans le Skype pour obtenir une documentation Business Server Management Shell.
  
## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Dépannage de l’Installation du plug-in sur Windows Server 2008 R2
<a name="MFA"> </a>

En cas d’échec de l’installation du plug-in sur un ordinateur exécutant Windows Server 2008 R2, vous devrez peut-être modifier le paramètre de sécurité d’Internet Explorer ou le paramètre de clé de Registre DisableMSI.
  
### <a name="modify-the-security-setting-in-internet-explorer"></a>Modification du paramètre de sécurité dans Internet Explorer

1. Ouvrez Internet Explorer.
    
2. Cliquez sur **Outils **, sur **Options Internet **, puis sur **Avancé **.
    
3. Faites défiler la page vers le bas jusqu'à la section **Sécurité**.
    
4. Désactivez la case à cocher **Ne pas enregistrer les pages chiffrées sur le disque**, puis cliquez sur **OK **.
    
    > [!NOTE]
    > Si sélectionné, ce paramètre provoque également une erreur lorsque vous tentez de télécharger une pièce jointe à partir de Skype pour Business Web App. 
  
5. Rejoignez la réunion. Le plug-in doit se télécharger sans erreurs.
    
### <a name="modify-the-disablemsi-registry-setting"></a>Modification du paramètre de Registre DisableMSI

1. Cliquez sur **Démarrer **, puis sur **Exécuter **.
    
2. Pour accéder à l'Éditeur du registre, tapez **regedit **.
    
3. Accédez à HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.
    
4. Modifiez ou ajoutez la clé de Registre DisableMSI de type REG_DWORD, et affectez-lui la valeur 0.
    
5. Rejoignez la réunion.
    
## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional"></a>Activation de l'application Réunions Skype pour remplacer Skype Entreprise Web App (facultatif)
<a name="SMA_Enable"> </a>

Cette procédure est facultative. Si vous ne l’utilisez pas, les utilisateurs externes continuera à participer à des conférences à l’aide de Skype pour Business Web App. 
  
### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Activation de la participation simplifiée aux réunions et l'application Réunions Skype

1. Lorsque vous activez l’accès pour le réseau CDN (Content Delivery), les utilisateurs auront la possibilité de se connecter en ligne CDN et application de réunions Skype et utilisez simplifié expérience de jointure de la réunion. 
    
   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Autoriser le client télémétrie de journalisation côté de la réunion de joindre une page web ou l’application de réunions Skype à envoyer aux serveurs de Microsoft (la commande false par défaut). 
    
   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Informations envoyées à Microsoft sont en stricte conformité avec [Skype pour entreprise de collecte de données](https://support.office.com/en-us/article/Skype-for-Business-data-collection-practices-c17e8ea6-b83b-4345-9401-47a6c8b13aad?ui=en-US&amp;rs=en-US&amp;ad=US).
    
3. Définir le délai d’attente avant le passage à la Skype hébergé localement pour une expérience d’entreprise Web App CDN n’est pas disponible. La valeur par défaut est de 6 secondes. Si celle-ci est définie sur 0, il n'y a pas de délai.
    
   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a>Voir aussi
<a name="SMA_Enable"> </a>

#### 

[Planifier des clients de réunions (Web App et réunions App)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)
  
[Planifier des clients de réunions (Web App et réunions App)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)
#### 

[Configuration de la Page d’inscription de réunion](http://technet.microsoft.com/library/45880423-47f4-49af-b825-cbd8e3fc1046.aspx)
  
[Déclaration de confidentialité de Microsoft Online Services](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)
  
[Termes du contrat de licence et la Documentation](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)

