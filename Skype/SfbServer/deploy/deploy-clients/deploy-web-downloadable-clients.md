---
title: Déploiement de clients Web téléchargeables dans Skype entreprise Server
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
description: 'Résumé : déployez Skype entreprise Web App et l’application réunions Skype utilisée avec Skype entreprise.'
ms.openlocfilehash: 16a2a28bf634524d6f61ba579652a6dddfd06de3
ms.sourcegitcommit: 0ad2fb145496210b728034d291a456b4caabdbf9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429420"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Déploiement de clients Web téléchargeables dans Skype entreprise Server

**Résumé :** Déployez l’application Web Skype entreprise 2015 et l’application réunions Skype utilisées avec Skype entreprise Server.

Skype entreprise Web App est un client Web IIS (Internet Information Services) installé sur le serveur qui exécute Skype entreprise Server et, par défaut, il est déployé à la demande pour les utilisateurs qui n’ont pas encore le client Skype entreprise. Ces utilisateurs de réunion sont plus souvent connectés depuis l’extérieur de votre réseau. Chaque fois qu’un utilisateur clique sur une URL de réunion mais que le client Skype entreprise n’est pas installé, l’utilisateur est invité à participer à la réunion à l’aide de la dernière version de Skype entreprise Web App, de l’application réunions Skype ou de Skype entreprise pour Mac.

Les fonctionnalités vocales, vidéo et de partage dans Skype entreprise Web App nécessitent un contrôle Microsoft ActiveX qui est utilisé comme plug-in par le navigateur de l’utilisateur. Vous pouvez installer le contrôle ActiveX à l’avance ou autoriser les utilisateurs à l’installer lorsque vous y êtes invité, qui se produit la première fois qu’ils utilisent Skype entreprise Web App ou la première fois qu’ils accèdent à une fonctionnalité nécessitant le contrôle ActiveX.

> [!NOTE]
> Dans les déploiements de serveur Edge de Skype entreprise Server, un proxy inverse HTTPs dans le réseau de périmètre est requis pour l’accès au client Skype entreprise Web App. Vous devez également publier des URL simples. Pour plus d’informations, reportez-vous à la rubrique [Configuration des serveurs de proxy inverse](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) et [des exigences DNS pour les URL simples dans Skype entreprise Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Activer l’authentification multifacteur pour Skype entreprise Web App
<a name="MFA"> </a>

Skype entreprise Web App, l’application réunions Skype et Skype entreprise pour Mac prennent en charge l’authentification multifacteur. Outre le nom d’utilisateur et le mot de passe, vous pouvez exiger des méthodes d’authentification supplémentaires, telles que des cartes à puce ou des codes confidentiels, pour authentifier les utilisateurs qui rejoignent des réseaux externes lorsqu’ils se connectent à des réunions Skype entreprise. Vous pouvez activer l’authentification multifacteur en déployant le serveur de fédération AD FS (Active Directory Federation Service) et en activant l’authentification passive dans Skype entreprise Server. Une fois les services ADFS configurés, les utilisateurs externes qui tentent de participer à des réunions Skype entreprise sont présentés avec une page Web d’authentification multifacteur AD FS qui contient le nom d’utilisateur et le mot de passe, ainsi que les autres méthodes d’authentification que vous avez configurées.

> [!IMPORTANT]
> Vous trouverez ci-dessous des considérations importantes si vous envisagez de configurer les services AD FS pour l’authentification multifacteur :

- L’authentification multifacteur ADFS fonctionne si le participant à la réunion et l’organisateur sont tous deux dans la même organisation ou s’ils proviennent d’une organisation fédérée AD FS. L’authentification multifacteur ADFS ne fonctionne pas pour les utilisateurs fédérés Lync car l’infrastructure Web Lync Server ne la prend pas en charge actuellement.

- Si vous utilisez des programmes d’équilibrage de la charge matérielle, activez la persistance des cookies sur les programmes d’équilibrage de la charge de sorte que toutes les demandes provenant de Skype entreprise Web App ou des clients d’application de réunion soient gérées par le même serveur frontal.

- Lorsque vous établissez une approbation de partie de confiance entre les serveurs Skype entreprise Server et AD FS, affectez une durée de vie du jeton suffisamment longue pour couvrir la longueur maximale de vos réunions Skype entreprise. Une durée de vie de jeton de 240 minutes est généralement suffisante.

- Cette configuration ne s’applique pas aux clients mobiles Lync.

### <a name="configure-multi-factor-authentication"></a>Configurer l’authentification multifacteur

1. Installez un rôle de serveur de fédération AD FS. Pour plus d’informations, voir le [Guide de déploiement des services de fédération Active Directory (AD FS) 2,0](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. Créer des certificats pour AD FS. Pour plus d’informations, consultez la section [« certificats de serveur de Fédération »](https://go.microsoft.com/fwlink/p/?LinkId=285376) de la rubrique plan for and Deploy AD FS for use with Single Sign-on.

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

## <a name="disable-branchcache"></a>Désactiver BranchCache
<a name="MFA"> </a>

La fonctionnalité BranchCache dans Windows 7 et Windows Server 2008 R2 peut interférer avec les composants Web de Skype entreprise Web App. Pour éviter les problèmes pour les utilisateurs de Skype entreprise Web App, assurez-vous que BranchCache n’est pas activé.

Pour plus d’informations sur la désactivation de BranchCache, voir le [Guide de déploiement de BranchCache](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).

## <a name="verifying-skype-for-business-web-app-deployment"></a>Vérification du déploiement de Skype entreprise Web App
<a name="MFA"> </a>

Vous pouvez utiliser l’applet de commande Test-CsUcwaConference pour vérifier que deux utilisateurs de test peuvent participer à une conférence à l’aide de l’API UCWA (Unified Communications Web API). Pour plus d’informations sur cette applet de commande, voir [test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) dans la documentation de Skype entreprise Server Management Shell.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Résolution des problèmes d’installation de plug-in sur Windows Server 2008 R2
<a name="MFA"> </a>

Si l’installation du plug-in échoue sur un ordinateur exécutant Windows Server 2008 R2, vous devrez peut-être modifier le paramètre de sécurité Internet Explorer ou le paramètre de clé de Registre DisableMSI.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Modifier le paramètre de sécurité dans Internet Explorer

1. Ouvrez Internet Explorer.

2. Cliquez sur **Outils**, sur **Options Internet**, puis sur **Avancé**.

3. Faites défiler la page vers le bas jusqu’à la section **Sécurité**.

4. Désactivez la case à cocher **Ne pas enregistrer les pages chiffrées sur le disque**, puis cliquez sur **OK**.

    > [!NOTE]
    > Si ce paramètre est sélectionné, un message d’erreur s’affichera également lors de la tentative de téléchargement d’une pièce jointe à partir de Skype entreprise Web App.

5. Rejoignez la réunion. Le plug-in doit se télécharger sans erreurs.

### <a name="modify-the-disablemsi-registry-setting"></a>Modifier le paramètre de Registre DisableMSI

1. Cliquez sur **Démarrer**, puis sur **Exécuter**.

2. Pour accéder à l’Éditeur du Registre, tapez **regedit**.

3. Accédez à HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.

4. Modifiez ou ajoutez la clé de Registre DisableMSI de type REG_DWORD, et affectez-lui la valeur 0.

5. Rejoignez la réunion.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Activer l’application réunions Skype pour remplacer Skype entreprise Web App (facultatif, Skype entreprise Server 2015 uniquement)
<a name="SMA_Enable"> </a>

Cette procédure est facultative et s’applique à Skype entreprise Server 2015 CU5 et versions ultérieures. Si vous ne l’utilisez pas, les utilisateurs externes continueront de participer à des réunions à l’aide de Skype entreprise Web App.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Activer la participation simplifiée à une réunion et l’application réunions Skype

1. Lorsque vous activez l’accès au réseau de distribution de contenu (CDN), les utilisateurs peuvent se connecter au CDN en ligne et obtenir une application de réunion Skype (sur Windows) et Skype entreprise pour Mac (sur Mac) et utiliser l’expérience de participation aux réunions simplifiée.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Autoriser la télémétrie de journalisation côté client à partir de la page Web de participation à la réunion ou de l’application réunions Skype à envoyer aux serveurs Microsoft (la commande est définie sur false par défaut).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Les informations envoyées à Microsoft sont strictement conformes à la [confidentialité et à Microsoft teams](../../../../Teams/teams-privacy.md).

3. Définissez le délai d’attente avant de revenir à l’expérience Skype entreprise Web hébergée localement si le CDN n’est pas disponible. La valeur par défaut est de 6 secondes. Si cette valeur est définie sur 0, il n’y aura pas de délai d’attente.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> Avec MeetingUxUseCdn dans la mise à jour cumulative 5 de Skype entreprise Server 2015, la valeur par défaut est définie sur false. Cela provoque un problème où le client Skype entreprise pour Mac est incapable de joindre des réunions de partenaires non fédéré en tant qu’invité, même si l’administrateur de Skype entreprise a défini MeetingUxUseCdn sur true. Pour que cela fonctionne, Skype entreprise Server 2015 doit avoir la mise à jour cumulative 7, 6.0.9319.534 ou une version ultérieure. [Pour remplacer Skype entreprise Web App dans Skype entreprise Server 2015, consultez la rubrique Enable Skype Meeting App](https://support.microsoft.com/kb/4132312).


## <a name="see-also"></a>Voir aussi
<a name="SMA_Enable"> </a>

[Planifier les clients des réunions (application Web et application de réunion)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Configuration de la page de participation aux réunions dans Skype entreprise Server](../../manage/conferencing/meeting-join-page.md)

[Déclaration de confidentialité de Microsoft](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[Termes du contrat de licence et documentation](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
