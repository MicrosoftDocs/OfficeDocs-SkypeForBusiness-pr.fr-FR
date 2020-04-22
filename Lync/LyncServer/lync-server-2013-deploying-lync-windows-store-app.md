---
title: 'Lync Server 2013 : déploiement de l’application Lync Windows Store'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4478f60fc99304e7cf882ddec7951aa3625d74f2
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a>Déploiement de l’application Lync Windows Store dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-12-03_

Avant de rendre l’application Lync Windows Store accessible aux utilisateurs, assurez-vous que votre déploiement est conforme à la [Configuration requise de l’application Lync pour Windows Store pour Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md). Pour plus d’informations sur la configuration de Lync Server 2013 afin de prendre en charge l’application Lync Windows Store, voir l’article du blog NextHop, « Lync Server Autodiscover and [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966)the Lync Windows Store App », à l’adresse. Une fois que votre environnement serveur est correctement configuré, vous pouvez demander aux utilisateurs de télécharger l’application Lync à partir du Windows Store en recherchant « Lync ».

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a>Activation de l’authentification multifacteur pour l’application Lync Windows Store

Mises à jour cumulatives pour Lync Server 2013 : le 2013 juin ajoute la prise en charge de l’authentification multifacteur pour les clients de l’application Windows Store de Lync. Outre le nom d’utilisateur et le mot de passe, vous pouvez exiger des méthodes d’authentification supplémentaires, telles que des cartes à puce ou des codes confidentiels, pour authentifier les utilisateurs externes lorsqu’ils se connectent à des réunions Lync. Pour activer l’authentification multifacteur, vous devez déployer le serveur de fédération AD FS (Active Directory Federation Service) et activer l’authentification passive dans Lync Server 2013. Une fois les services ADFS configurés, les utilisateurs externes qui tentent de participer à des réunions Lync sont présentés avec une page Web d’authentification multifacteur AD FS qui contient le nom d’utilisateur et le mot de passe, ainsi que les autres méthodes d’authentification que vous avez configurées.

<div class=" ">


> [!IMPORTANT]  
> Vous trouverez ci-dessous des considérations importantes si vous envisagez de configurer AD FS pour l’authentification multifacteur pour l’application Lync Windows Store : 
> <UL>
> <LI>
> <P>Lync Server 2013 avec des mises à jour cumulatives pour Lync Server 2013 : le 2013 juin est requis au minimum. Les clients de bureau Lync 2013 n’ont pas besoin de mises à jour cumulatives pour Lync Server 2013 : le 2013 juin, de sorte qu’il semble que l’authentification passive fonctionne car les clients Lync 2013 peuvent s’authentifier. Toutefois, le processus d’authentification pour les clients d’application Lync Windows Store ne se termine pas et aucune notification ni message d’erreur ne s’affiche.</P>
> <LI>
> <P>Le serveur doit être configuré de sorte que l’authentification passive soit le seul type d’authentification offert.</P>
> <LI>
> <P>Si vous utilisez des programmes d’équilibrage de la charge matérielle, activez la persistance des cookies sur les programmes d’équilibrage de la charge afin que toutes les demandes du client d’application Lync du Windows Store soient gérées par le même serveur frontal.</P>
> <LI>
> <P>Lorsque vous établissez une approbation de partie de confiance entre les serveurs Lync Server et AD FS, affectez une durée de vie de jeton suffisamment longue pour couvrir la longueur maximale de vos réunions Lync. Une durée de vie de jeton de 240 minutes est généralement suffisante.</P></LI></UL>



</div>

**Pour configurer l’authentification multifacteur**

1.  Installez un rôle de serveur de fédération AD FS. Pour plus d’informations, consultez le Guide de déploiement des services de <https://go.microsoft.com/fwlink/p/?linkid=267511>Fédération Active Directory (AD fs) 2,0 à l’adresse.

2.  Créer des certificats pour AD FS. Pour plus d’informations, consultez la section « certificats de serveur de Fédération » de la rubrique plan for and Deploy AD FS for use with Single Sign [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376)-on.

3.  À partir de l’interface de ligne de commande Windows PowerShell, exécutez la commande suivante :
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  Établissez un partenariat en exécutant la commande suivante :
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  Définissez les règles de partie de confiance suivantes :
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a>Problèmes connus pouvant empêcher la connexion

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a>La date et l’heure ne sont pas définies correctement sur l’appareil exécutant l’application Lync du Windows Store

Le paramètre de l’heure sur l’appareil doit être synchronisé avec le paramètre heure sur le serveur. Ceci est particulièrement important pour les appareils tels que Microsoft surface, ainsi que d’autres appareils exécutant Windows RT qui ne sont pas liés à un domaine. Pour définir l’heure sur ces appareils automatiquement à partir d’un serveur de temps, exécutez la commande suivante à partir d’une invite de commandes avec élévation de privilèges sur l’appareil :
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a>L’application Lync du Windows Store ne peut pas accéder au serveur ou aux services Lync

L’application Lync du Windows Store n’est peut-être pas en mesure d’accéder au serveur ou aux services Lync par le biais de cartes réseau, telles que des modems USB 4G LTE, qui ne sont pas enregistrés avec Windows 8 en tant que périphériques physiques. L’application Lync du Windows Store peut présenter ce problème même si les applications de bureau et les navigateurs peuvent accéder à d’autres serveurs et sites Web.

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a>L’application Lync du Windows Store ne peut pas se connecter avec Lync Server 2010 et le serveur Edge Office Communications Server 2007 R2

Si votre topologie se compose de Lync Server 2010 avec le serveur Edge Office Communications Server 2007 R2, vous devrez exécuter la version mise à jour du générateur de topologies disponible dans la mise à jour cumulative de Lync Server 2010 : juillet 2013. Les versions antérieures du générateur de topologie ne créent pas le mappage requis sur le serveur Edge Office Communications Server 2007, de sorte que les clients d’application Lync Windows Store ne peuvent pas se connecter. Les étapes suivantes sont nécessaires :

1.  Installez la mise à jour cumulative pour Lync Server 2010 : juillet 2013 sur les pools Lync Server 2010 et les directeurs Lync Server 2010.

2.  Mettez à jour la configuration de découverte automatique Lync pour indiquer que le point d’entrée SIP externe est l’adresse du serveur Edge en procédant comme suit :
    
    1.  Ouvrez Lync Server Management Shell.
    
    2.  Exécutez la commande suivante :
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a>L’application Lync du Windows Store ne peut pas se connecter en raison d’un échec de validation de nom de certificat

Un problème de connexion peut se produire pour les utilisateurs de Microsoft 365 ou Office 365 qui n’exécutent pas la dernière version de l’application Lync du Windows Store. Ce problème se produit généralement lorsque vous utilisez plusieurs domaines (par exemple, lorsque l’URI SIP est **usera@domainZ.com** mais que le serveur Edge est **SIP.domainX.com**). Pour résoudre le problème, les utilisateurs doivent installer la dernière version de l’application Lync du Windows Store, qui nécessite également Windows 8,1.

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a>Utiliser les journaux d’applications Lync Windows Store pour résoudre les problèmes

Vous pouvez utiliser les journaux générés sur l’appareil pour résoudre les problèmes. Les journaux sont stockés dans le dossier suivant :

% Des packages\\\\% LocalAppData% Microsoft\_.\\LyncMX\\8wekyb3d8bbwe suivi des LocalState

Avant d’obtenir les journaux d’un utilisateur, vérifiez que la journalisation est activée, puis demandez à l’utilisateur d’enregistrer les journaux de sorte que toutes les informations stockées dans la mémoire soient également enregistrées dans des fichiers sur le disque dur.

**Pour activer la journalisation**

1.  Ouvrez l’application Lync Windows Store sur l’appareil.

2.  Faire glisser à partir du côté droit de l’écran. Si vous utilisez une souris, pointez sur le coin supérieur droit de l’écran, puis déplacez le pointeur de la souris vers le bas de l’écran.

3.  Sélectionnez **paramètres**, sélectionnez **options**, puis définissez les **journaux** de diagnostic **sur activé**.

4.  Si les **journaux de diagnostic** étaient désactivés précédemment, vous devez redémarrer Lync. Pour redémarrer Lync, effectuez l’une des opérations suivantes :
    
      - Redémarrez l’appareil.
    
      - Terminez la tâche Lync et relancez l’application. Pour mettre fin à la tâche, ouvrez le gestionnaire des tâches de Windows, sélectionnez **Lync**, puis cliquez sur **fin de tâche**. Si Lync n’est pas disponible, cliquez sur **plus de détails** et recherchez Lync sous **processus en arrière-plan**.

**Pour enregistrer les journaux**

1.  Ouvrez l’application Lync Windows Store sur l’appareil.

2.  Essayez de vous connecter.

3.  Faire glisser à partir du côté droit de l’écran. Si vous utilisez une souris, pointez sur le coin supérieur droit de l’écran, puis déplacez le pointeur de la souris vers le bas de l’écran.

4.  Sélectionnez **paramètres**, **à propos**de, puis sélectionnez **enregistrer les journaux**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

