---
title: Configuration de Microsoft Lync Server 2013 dans un environnement intersites
TOCTitle: Configuration de Microsoft Lync Server 2013 dans un environnement intersites
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204990(v=OCS.15)
ms:contentKeyID: 49297605
ms.date: 02/23/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de Microsoft Lync Server 2013 dans un environnement intersites

 

_**Dernière rubrique modifiée :** 2017-02-21_

Dans une configuration intersite, certains de vos utilisateurs sont hébergés sur une installation locale de Microsoft Lync Server 2013 tandis que d’autres le sont sur la version Office 365 de Lync Server. Afin de configurer une authentification de serveur à serveur dans un environnement intersite, vous devez d’abord configurer votre installation locale de Lync Server 2013 afin d’approuver le serveur d’autorisation Office 365. La première étape de ce processus peut être effectuée en exécutant le script Lync Server Management Shell suivant :

    $TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
    
    $sts = Get-CsOAuthServer microsoft.sts -ErrorAction SilentlyContinue
            
       if ($sts -eq $null)
          {
             New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
          }
       else
          {
             if ($sts.MetadataUrl -ne  "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1")
                {
                   Remove-CsOAuthServer microsoft.sts
                   New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
                }
            }
    
    $exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
            
    if ($exch -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer
        }
    else
        {
           if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.exchange
                 New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer 
              }
           else
              {
                 Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full -UseOAuthServer
              }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

N’oubliez pas que le nom de domaine d’un client est généralement différent du nom de l’organisation ; en fait, le nom de domaine est presque toujours identique à l’ID de client. C’est pourquoi la première ligne du script est utilisée pour retourner la valeur de la propriété TenantId du client spécifié (ici, fabrikam.com), puis pour attribuer ce nom à la variable $TenantId :

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

Une fois que le script s’est exécuté, vous devez configurer une relation d’approbation entre Lync Server 2013 et le serveur d’autorisation, puis une seconde relation d’approbation entre Exchange 2013 et le serveur d’autorisation. Vous pouvez uniquement le faire à l’aide d’applets de commande Microsoft Online Services.

> [!NOTE]  
> Si vous n’avez pas installé les applets de commande Microsoft Online Services, vous avez deux choses à faire avant de poursuivre. Tout d’abord, téléchargez et installez la version 64 bits de l’Assistant de connexion Microsoft Online Services. Une fois l’installation terminée, téléchargez et installez la version 64 bits du module Microsoft Online Services pour Windows PowerShell. Des informations détaillées sur l’installation et l’utilisation du module Microsoft Online Services sont disponibles sur le site web d’Office 365. Ces instructions vous indiquent également comment configurer l’authentification unique, la fédération et la synchronisation entre Office 365 et Active Directory.<br />
Si vous n'avez pas installé ces applets de commande, votre script échouera car l'applet de commande Get-CsTenant ne sera pas disponible.

Après avoir configuré Office 365 et après avoir créé des principaux du service Office 365 pour Lync Server 2013 et Exchange 2013, vous devez alors enregistrer vos informations d’identification auprès de ces principaux du service. Pour ce faire, vous devez d’abord obtenir un certificat X.509 Base64 enregistré sous forme de fichier .CER. Ce certificat est ensuite appliqué aux principaux du service Office 365.

Lorsque vous avez obtenu le certificat X.509, démarrez le module Microsoft Online Services (cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft Online Services**, puis sur **Module Microsoft Online Services pour Windows PowerShell**). Une fois que le module Services s’ouvre, tapez ce qui suit pour importer le module Microsoft Online Windows PowerShell contenant les applets de commandes utilisables pour gérer les principaux du service :

    Import-Module MSOnlineExtended

Lorsque le module a été importé, tapez la commande suivante, puis appuyez sur Entrée afin de vous connecter à Office 365 :

    Connect-MsolService

Après avoir appuyé sur Entrée, une boîte de dialogue d’informations d’identification s’affiche. Entrez-y votre nom d’utilisateur et votre mot de passe Office 365, puis cliquez sur OK.

Dès que vous êtes connecté à Office 365, vous pouvez exécuter la commande suivante afin de retourner des informations sur vos principaux du service :

    Get-MsolServicePrincipal

Vous devriez obtenir des informations similaires à celles-ci pour tous vos principaux du service :

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

L’étape suivante consiste à importer, encoder et assigner le certificat X.509. Pour importer et encoder le certificat, utilisez les commandes Windows PowerShell suivantes, en veillant à spécifier le chemin d’accès complet à votre fichier .CER lorsque vous appelez la méthode Import :

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

Une fois que le certificat a été importé et encodé, vous pouvez l’assigner à vos principaux du service Office 365. Pour cela, commencez par utiliser Get-MsolServicePrincipal pour récupérer la valeur de la propriété AppPrincipalId des principaux du service Lync Server et Microsoft Exchange ; la valeur de la propriété AppPrincipalId sert à identifier le principal du service auquel est assigné le certificat. Avec la valeur de la propriété AppPrincipalId de Lync Server 2013 à portée de main, utilisez la commande suivante pour assigner le certificat à la version Office 365 de Lync Server (les propriétés StartDate et EndDate doivent correspondre à la période de validité du certificat) :

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

Vous devez ensuite répéter la commande, cette fois en utilisant la valeur de la propriété AppPrincipalId de Exchange 2013.

Si vous avez besoin de supprimer ce certificat ultérieurement, vous pouvez le faire en récupérant la propriété KeyId du certificat au préalable :

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

Cette commande retourne des données comme les suivantes :

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

Vous pouvez ensuite supprimer le certificat à l’aide d’une commande similaire à celle-ci :

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

En plus d’assigner un certificat, vous devez également configurer le principal du service Exchange Online et configurer la version locale de Lync Server 2013 en tant que principal du service Office 365. Pour ce faire, exécutez les deux commandes suivantes :

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

