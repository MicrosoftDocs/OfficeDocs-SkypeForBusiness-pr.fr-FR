---
title: 'Lync Server 2013 : configuration de l’authentification passive'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a2e52f957a8aba7e69e97b0ec2100ffbc5a190c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a>Configuration de l’authentification passive de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-11_

La section suivante décrit comment configurer Lync Server 2013 avec des mises à jour cumulatives : 2013 juillet pour prendre en charge l’authentification passive. Une fois activé, les utilisateurs de Lync qui sont activés pour l’authentification à deux facteurs seront obligés d’utiliser une carte à puce physique ou virtuelle et un code confidentiel valide pour se connecter à l’aide de la 2013 Lync avec des mises à jour cumulatives : client 2013 de juillet.

<div class="">


> [!NOTE]  
> Il est vivement recommandé que les clients activent l’authentification passive pour les services Serveur d’inscriptions et web au niveau du service. Si l’authentification passive est activée pour le Bureau d’enregistrement et les services Web au niveau global, il est probable que les échecs d’authentification à l’échelle de l’organisation s’affichent pour les utilisateurs qui ne se connectent pas à la 2013 Lync avec des mises à jour cumulatives : client de bureau du client de juillet 2013.



</div>

<div>

## <a name="web-service-configuration"></a>Configuration des services web

La procédure ci-dessous décrit la création d’une configuration de service web personnalisée pour les directeurs, les pools d’entreprise et les serveurs Standard Edition pour lesquels l’authentification passive sera activée.

**Pour créer une configuration de service web personnalisée**

1.  Connectez-vous à votre Lync Server 2013 avec des mises à jour cumulatives : serveur frontal 2013 juillet à l’aide d’un compte d’administrateur Lync.

2.  Lancez Lync Server 2013 Management Shell.

3.  À partir de la ligne de commande de Lync Server Management Shell, créez une nouvelle configuration de service Web pour chaque directeur, pool d’entreprise et serveur Standard Edition qui sera activé pour l’authentification passive en exécutant la commande suivante :
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > La valeur du nom de domaine complet WsFedPassiveMetadataUri correspond au nom du service de fédération de votre serveur AD FS 2.0. Pour consulter la valeur Nom du service de fédération dans la console de gestion AD FS 2.0, cliquez avec le bouton droit sur <STRONG>Service</STRONG> dans le volet de navigation, puis sélectionnez <STRONG>Modifier les propriétés du service de fédération</STRONG>.

    
    </div>

4.  Vérifiez que les valeurs UseWsFedPassiveAuth et WsFedPassiveMetadataUri ont été définies correctement en exécutant la commande suivante :
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  Pour les clients, l’authentification passive est la méthode d’authentification la moins privilégiée pour l’authentification de ticket web. Pour tous les directeurs, les pools d’entreprise et les serveurs Standard Edition qui seront activés pour l’authentification passive, tous les autres types d’authentification doivent être désactivés dans Lync Web services en exécutant la commande suivante :
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  Vérifiez que tous les autres types d’authentification ont été désactivés en exécutant la commande suivante :
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a>Configuration du serveur proxy

Lorsque l’authentification par certificat est désactivée pour les services Web Lync, le client Lync utilise un type d’authentification moins favori, tel que Kerberos ou NTLM, pour s’authentifier auprès du service d’inscription. L’authentification par certificat est toujours nécessaire pour permettre au client Lync de récupérer un webticket, toutefois, Kerberos et NTLM doivent être désactivés pour le service d’inscription.

La procédure ci-dessous décrit la création d’une configuration de proxy personnalisée pour les pools Edge, les pools d’entreprise et les serveurs Standard Edition pour lesquels l’authentification passive sera activée.

**Pour créer une configuration de proxy personnalisée**

1.  À partir de la ligne de commande de Lync Server Management Shell, créez une nouvelle configuration de proxy pour chaque 2013 de Lync Server avec des mises à jour cumulatives : le pool de périphériques de juillet 2013, le pool d’entreprise et le serveur Standard Edition, qui seront activés pour l’authentification passive en exécutant le commandes suivantes :
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  Vérifiez que tous les autres types d’authentification proxy ont été désactivés correctement en exécutant la commande suivante :
    ```powershell
    Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
     ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

