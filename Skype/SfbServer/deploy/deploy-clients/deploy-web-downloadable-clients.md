---
title: Déploiement de clients Web à télécharger dans Skype entreprise Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Résumé : déploiement de l’application Skype entreprise Web App et de réunions Skype utilisée avec Skype entreprise.'
ms.openlocfilehash: 5f4cc14ab3774096846053e6da41647c1987a1dd
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768957"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Déploiement de clients Web à télécharger dans Skype entreprise Server

**Résumé :** Déploiement de l’application Web Skype entreprise 2015 et de réunions Skype utilisée avec Skype entreprise Server.

Skype entreprise Web App est un client Web Internet Information Services (IIS) installé sur le serveur exécutant Skype entreprise Server et par défaut, il est déployé à la demande pour les utilisateurs qui n’ont pas encore le client Skype entreprise. Il est plus souvent possible de se connecter à l’extérieur de votre réseau. Dès qu’un utilisateur clique sur l’URL d’une réunion, mais que le client Skype entreprise n’est pas installé, l’utilisateur est invité à rejoindre la réunion à l’aide de la version la plus récente de Skype entreprise Web App, de l’application réunions Skype ou de Skype entreprise pour Mac.

Les fonctionnalités de voix, de vidéo et de partage dans Skype entreprise Web App requièrent un contrôle Microsoft ActiveX utilisé comme plugin par le navigateur de l’utilisateur. Lorsque vous y êtes invité, vous pouvez installer le contrôle ActiveX à l’avance ou permettre aux utilisateurs de l’installer lorsque vous y êtes invité pour la première fois sur Skype entreprise Web App ou lorsque la première fois qu’ils ont accès à une fonctionnalité nécessitant le contrôle ActiveX.

> [!NOTE]
> Dans les déploiements de serveur Edge Skype entreprise Server, un proxy HTTPs inverse dans le réseau de périmètre est requis pour l’accès au client Skype entreprise Web App. Vous devez également publier des URL simples. Pour plus d’informations, reportez-vous à la rubrique [configuration de serveurs proxy inverse](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) et [de configurations DNS requises pour des URL simples dans Skype entreprise Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Activer l’authentification multifacteur dans Skype entreprise Web App
<a name="MFA"> </a>

Skype entreprise Web App, l’application réunions Skype et Skype entreprise pour Mac prennent en charge l’authentification multifacteur. Outre le nom d’utilisateur et le mot de passe, vous pouvez demander des méthodes d’authentification supplémentaires, telles que des cartes à puce ou des épingles, afin d’authentifier les utilisateurs qui se connectent à partir de réseaux extérieurs lors de leur connexion aux réunions Skype entreprise. Vous pouvez activer l’authentification multifacteur via le déploiement du serveur de fédération AD FS (Active Directory Federation Services) et l’activation de l’authentification passive dans Skype entreprise Server. Une fois AD FS configuré, les utilisateurs externes qui essaient de participer à des réunions Skype entreprise sont dotés d’une page Web d’authentification multifacteur AD FS contenant le nom d’utilisateur et le mot de passe, ainsi que toutes les méthodes d’authentification supplémentaires que vous configuré.

> [!IMPORTANT]
> Vous trouverez ci-dessous des considérations importantes si vous envisagez de configurer les services AD FS pour l’authentification multifacteur :

- L'authentification ADFS multifacteur fonctionne si le participant à la réunion et l'organisateur appartiennent à la même organisation ou à une organisation fédérée AD FS. Elle ne fonctionne pas pour les utilisateurs fédérés Lync, car l’infrastructure web du serveur Lync ne la prend pas en charge pour le moment.

- Si vous utilisez des équilibreurs de charge matérielle, activez la persistance des cookies sur les équilibreurs de charge de sorte que toutes les demandes des clients de l’application Skype entreprise Web App ou réunions soient gérées par le même serveur principal.

- Lorsque vous établissez une relation d’approbation de la partie de confiance entre les serveurs Skype entreprise Server et AD FS, vous devez affecter une durée de vie de jeton suffisamment longue pour pouvoir prolonger la durée maximale de votre réunion Skype entreprise. Une durée de vie de jeton de 240 minutes est généralement suffisante.

- Cette configuration ne s’applique pas aux clients mobiles Lync.

### <a name="configure-multi-factor-authentication"></a>Configuration de l'authentification multifacteur

1. Installez un rôle de serveur de fédération AD FS. Pour plus d’informations, voir le [Guide de déploiement de services ADFS (Active Directory Federation Services) 2,0](https://go.microsoft.com/fwlink/p/?linkid=267511) .

2. Créez des certificats pour AD FS. Pour plus d’informations, reportez-vous à la section [« certificat de serveur de Fédération »](https://go.microsoft.com/fwlink/p/?LinkId=285376) de la rubrique plan pour et déployer AD FS pour une utilisation avec la rubrique authentification unique.

3. À partir de l’interface de ligne de commande Windows PowerShell, exécutez la commande suivante :

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. Établissez un partenariat en exécutant la commande suivante :

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. Définissez les règles de partie de confiance suivantes :

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>Désactivation de BranchCache 
<a name="MFA"> </a>

La fonctionnalité BranchCache dans Windows 7 et Windows Server 2008 R2 peut interférer avec les composants WebPart de Skype entreprise Web App. Pour éviter des problèmes pour les utilisateurs de Skype entreprise Web App, assurez-vous que BranchCache n’est pas activé.

Pour plus d’informations sur la désactivation de BranchCache, voir le [Guide de déploiement de BranchCache](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).

## <a name="verifying-skype-for-business-web-app-deployment"></a>Vérification du déploiement de Skype entreprise Web App
<a name="MFA"> </a>

Vous pouvez utiliser l'applet de commande Test-CsUcwaConference pour vérifier que deux utilisateurs de test peuvent participer à une conférence à l'aide de l'API UCWA (Unified Communications Web API). Pour plus d’informations sur cette applet de connexion, voir [test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) dans la documentation de Skype entreprise Server Management Shell.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Résoudre les problèmes d’installation du plug-in sur Windows Server 2008 R2
<a name="MFA"> </a>

Si l’installation du plug-in échoue sur un ordinateur exécutant Windows Server 2008 R2, vous devrez peut-être modifier le paramètre de sécurité Internet Explorer ou le paramètre de clé de Registre DisableMSI.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Modification du paramètre de sécurité dans Internet Explorer

1. Ouvrez Internet Explorer.

2. Cliquez sur **Outils **, sur **Options Internet **, puis sur **Avancé **.

3. Faites défiler la page vers le bas jusqu'à la section **Sécurité**.

4. Désactivez la case à cocher **Ne pas enregistrer les pages chiffrées sur le disque**, puis cliquez sur **OK **.

    > [!NOTE]
    > Ce paramètre entraîne également une erreur lorsque vous tentez de télécharger une pièce jointe à partir de Skype entreprise Web App.

5. Rejoignez la réunion. Le plug-in doit se télécharger sans erreurs.

### <a name="modify-the-disablemsi-registry-setting"></a>Modification du paramètre de Registre DisableMSI

1. Cliquez sur **Démarrer **, puis sur **Exécuter **.

2. Pour accéder à l'Éditeur du registre, tapez **regedit **.

3. Accédez à HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.

4. Modifiez ou ajoutez la clé de Registre DisableMSI de type REG_DWORD, et affectez-lui la valeur 0.

5. Rejoignez la réunion.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Activation de l’application réunions Skype pour remplacer Skype entreprise Web App (facultatif, Skype entreprise Server 2015 uniquement)
<a name="SMA_Enable"> </a>

Cette procédure est facultative et s’applique à Skype entreprise Server 2015 CU5 et versions ultérieures. Si ce n’est pas le cas, les utilisateurs externes continuent à rejoindre des réunions à l’aide de Skype entreprise Web App.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Activation de la participation simplifiée aux réunions et l'application Réunions Skype

1. Lorsque vous activez l’accès au réseau de distribution de contenu (CDN), les utilisateurs peuvent se connecter au CDN en ligne et obtenir l’application réunions Skype (sur Windows) et Skype entreprise pour Mac (sur Mac) et utiliser l’interface de réunion simplifiée.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Autoriser la télémétrie de la journalisation côté client à partir de la page Web de participation à la réunion ou de l’application réunions Skype pour être envoyée aux serveurs Microsoft (la commande est définie sur false par défaut).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Les informations envoyées à Microsoft sont strictement conformes aux [pratiques en matière de collecte de données Skype entreprise](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).

3. Définissez le délai d’expiration avant de revenir à l’interface Web de Skype entreprise hébergée en local si le CDN n’est pas disponible. La valeur par défaut est de 6 secondes. Si celle-ci est définie sur 0, il n'y a pas de délai.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> Avec MeetingUxUseCdn dans Skype entreprise Server 2015 cumulative Update 5, la valeur par défaut est définie sur false. Le problème se produit alors lorsque le client Skype entreprise pour Mac ne peut pas participer à des réunions non fédérées de partenaires en tant qu’invité, même si l’administrateur Skype entreprise a défini MeetingUxUseCdn sur true. Pour que cette opération fonctionne, Skype entreprise Server 2015 doit disposer de la mise à jour cumulative 7, 6.0.9319.534 ou ultérieure. [Pour remplacer Skype entreprise Web App dans Skype entreprise Server 2015, voir Activer l’application réunions Skype](https://support.microsoft.com/kb/4132312).


## <a name="see-also"></a>Voir aussi
<a name="SMA_Enable"> </a>

[Planifier pour les clients de conférences (application Web et application réunions)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Configuration de la page de participation à une réunion dans Skype entreprise Server](../../manage/conferencing/meeting-join-page.md)

[Déclaration de confidentialité de Microsoft Online Services](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[Termes du contrat de licence et documentation](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
