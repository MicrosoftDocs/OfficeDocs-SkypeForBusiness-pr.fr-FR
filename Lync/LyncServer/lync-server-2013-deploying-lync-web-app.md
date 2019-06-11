---
title: 'Lync Server 2013: déploiement de Lync Web App'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ca2a0d2da0b10b8e60df8489b8cc0a584cd70e3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a>Déploiement de Lync Web App dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-07-18_

Lync Web App est un client Web Internet Information Services (IIS) qui s’installe avec Lync Server 2013 et est activé par défaut. Aucune étape supplémentaire n’est nécessaire pour activer Lync Web App sur le serveur ou déployer le client Web auprès des utilisateurs. Dès qu’un utilisateur clique sur l’URL d’une réunion, mais que le client 2013 Lync n’est pas installé, l’utilisateur est invité à rejoindre la réunion à l’aide de la version la plus récente de Lync Web App.

Les fonctionnalités de voix, de vidéo et de partage dans Lync Web App requièrent un contrôle Microsoft ActiveX. Lorsque vous y êtes invité, vous pouvez installer le contrôle ActiveX à l’avance ou permettre aux utilisateurs de l’installer lorsque la première fois qu’ils utilisent Lync Web App ou la première fois qu’ils ont accès à une fonctionnalité qui nécessite le contrôle ActiveX.

<div class=" ">


> [!NOTE]  
> Dans les déploiements de serveur Edge Lync Server 2013, un proxy HTTPs inverse dans le réseau de périmètre est requis pour l’accès au client Lync Web App. Vous devez également publier des URL simples. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">configuration de serveurs proxy inverse pour Lync server 2013</A> et <A href="lync-server-2013-planning-for-simple-urls.md">planification d’URL simples dans Lync Server 2013</A>.



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a>Activation de l’authentification multifacteur pour Lync Web App

La version 2013 de Lync Server de Lync Web App prend en charge l’authentification multifacteur. Outre le nom d’utilisateur et le mot de passe, vous pouvez demander des méthodes d’authentification supplémentaires, telles que des cartes à puce ou des épingles, afin d’authentifier les utilisateurs qui se connectent à partir de réseaux externes lors de leur connexion aux réunions Lync. Vous pouvez activer l’authentification multifacteur via le déploiement du serveur de fédération AD FS (Active Directory Federation Services) et l’activation de l’authentification passive dans Lync Server 2013. Après la configuration d’AD FS, les utilisateurs externes qui essaient de participer à des réunions Lync sont dotés d’une page Web d’authentification multifacteur AD FS contenant le nom d’utilisateur et le mot de passe, ainsi que d’autres méthodes d’authentification que vous avez configurées. .

<div class=" ">


> [!IMPORTANT]  
> Vous trouverez ci-dessous des considérations importantes si vous envisagez de configurer les services AD FS pour l’authentification multifacteur : 
> <UL>
> <LI>
> <P>L'authentification ADFS multifacteur fonctionne si le participant à la réunion et l'organisateur appartiennent à la même organisation ou à une organisation fédérée AD FS. Elle ne fonctionne pas pour les utilisateurs fédérés Lync, car l’infrastructure web du serveur Lync ne la prend pas en charge pour le moment.</P>
> <LI>
> <P>Si vous utilisez des équilibreurs de charge matérielle, activez la persistance des cookies sur les équilibreurs de charge de sorte que toutes les requêtes du client Lync Web App soient gérées par le même serveur principal.</P>
> <LI>
> <P>Lorsque vous établissez une relation d’approbation de la partie de confiance entre les serveurs Lync Server et AD FS, attribuez une durée de vie du jeton suffisamment longue pour couvrir la longueur maximale de vos réunions Lync. Une durée de vie de jeton de 240 minutes est généralement suffisante.</P>
> <LI>
> <P>Cette configuration ne s’applique pas aux clients mobiles Lync.</P></LI></UL>



</div>

**Pour configurer l’authentification multifacteur**

1.  Installez un rôle de serveur de fédération AD FS. Pour plus d’informations, consultez le Guide de déploiement de services ADFS (Active Directory Federation Services) 2,0 à l’adresse<http://go.microsoft.com/fwlink/p/?linkid=267511>

2.  Créez des certificats pour AD FS. Pour plus d’informations, reportez-vous à la section «certificats de serveur de Fédération» de la rubrique plan pour et déployer AD FS [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)pour une utilisation avec une connexion unique à l’adresse.

3.  À partir de l’interface de ligne de commande Windows PowerShell, exécutez la commande suivante:
    
        add-pssnapin Microsoft.Adfs.powershell

4.  Établissez un partenariat en exécutant la commande suivante :
    
        Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  Définissez les règles de partie de confiance suivantes :
    
       ```
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="branchcache-configuration"></a>Configuration de BranchCache

La fonctionnalité BranchCache dans Windows 7 et Windows Server 2008 R2 peut interférer avec les composants Web de Lync Web App. Pour éviter les problèmes liés aux utilisateurs Lync Web App, assurez-vous que BranchCache n’est pas activé.

Pour plus d’informations sur la désactivation de BranchCache, voir le Guide de déploiement de BranchCache, qui est disponible au format Word [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788) au centre de téléchargement Microsoft au format HTML, dans la bibliothèque technique [http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789)de Windows Server 2008 R2.

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a>Vérification du déploiement de Lync Web App

Vous pouvez utiliser l'applet de commande Test-CsUcwaConference pour vérifier que deux utilisateurs de test peuvent participer à une conférence à l'aide de l'API UCWA (Unified Communications Web API). Pour plus d’informations sur cette cmdlet, voir [test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) dans la documentation Lync Server Management Shell.

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a>Résoudre les problèmes d’installation du plug-in sur Windows Server 2008 R2

Si l’installation du plug-in échoue sur un ordinateur exécutant Windows Server 2008 R2, vous devrez peut-être modifier le paramètre de sécurité Internet Explorer ou le paramètre de clé de Registre DisableMSI.

**Pour modifier le paramètre de sécurité dans Internet Explorer**

1.  Ouvrez Internet Explorer.

2.  Cliquez sur **Outils **, sur **Options Internet **, puis sur **Avancé **.

3.  Faites défiler la page vers le bas jusqu'à la section **Sécurité**.

4.  Désactivez la case à cocher **Ne pas enregistrer les pages chiffrées sur le disque**, puis cliquez sur **OK **.
    
    <div class=" ">
    

    > [!NOTE]  
    > Si cette option est sélectionnée, ce paramètre entraîne également une erreur lors de la tentative de téléchargement d’une pièce jointe à partir de Lync Web App.

    
    </div>

5.  Rejoignez la réunion. Le plug-in doit se télécharger sans erreurs.

**Pour modifier le paramètre de Registre DisableMSI**

1.  Cliquez sur **Démarrer **, puis sur **Exécuter **.

2.  Pour accéder à l'Éditeur du registre, tapez **regedit **.

3.  Naviguez jusqu'\_à\_HKEY\\stratégies\\\\de logiciels\\de\\l’ordinateur local Microsoft Windows Installer.

4.  Modifiez ou ajoutez la clé de Registre DisableMSI de type\_reg DWORD et attribuez-lui la valeur 0.

5.  Rejoignez la réunion.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration de la page de participation à une réunion dans Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)  
[Plates-formes prises en charge par Lync Web App pour Lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

