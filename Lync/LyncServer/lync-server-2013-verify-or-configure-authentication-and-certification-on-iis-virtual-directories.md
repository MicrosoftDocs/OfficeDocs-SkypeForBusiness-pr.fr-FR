---
title: 'Lync Server 2013 : Vérification ou configuration de l’authentification et de la certification dans les répertoires virtuels des services Internet (IIS)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48399ed2a6eba53707218295adcd1cbd11a5e32c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a>Connexion d’un Survivable Branch Appliance à un pool de serveurs frontaux

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-05-25_

Suivez la procédure ci-dessous pour configurer le certificat sur les répertoires virtuels d’Internet Information Services (IIS) ou vérifier que le certificat est correctement configuré. Appliquez la procédure suivante à chaque serveur exécutant IIS dans votre pool de serveurs Lync interne et au directeur facultatif.

<div>


> [!NOTE]  
> La procédure suivante définit une procédure permettant de demander un certificat combiné qui est utilisé pour tous les rôles Lync Server, site Web interne et site Web externe dans IIS. Lync Server 2010 a présenté un ensemble d’applets de&nbsp;certification Windows PowerShell Lync Server Management Shell pour une vue rapide de la gestion de la demande de certificat, de l’importation et de l’affectation. La procédure suppose qu’il existe une autorité de certification déployée en interne (CA) qui peut traiter la demande. Si vous utilisez des certificats publics pour votre serveur Lync, ou si votre autorité de certification nécessite une demande hors connexion, voir la syntaxe détaillée de cette rubrique pour plus d’informations sur le paramètre – OUTPUT. <A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Requête-CsCertificate</A>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a>Pour configurer l’authentification et les certificats sur les répertoires virtuels IIS

1.  Pour pouvoir effectuer les opérations suivantes, vous devez être connecté à l’ordinateur (serveur frontal ou directeur) sur lequel les services Web sont installés et être un administrateur local. Vous devez disposer des autorisations de **lecture** et d' **inscription** sur l’autorité de certification auprès desquelles vous demandez des certificats, si celle-ci est l’autorité de certification de votre organisation. Vous n’avez pas besoin d’autorisations sur l’autorité de certification si vous allez configurer et envoyer une demande de certificat hors connexion.

2.  Cliquez sur **Démarrer**, sur **tous les programmes**, sélectionnez **Outils d’administration**, puis cliquez sur **Gestionnaire des services Internet (IIS)**.

3.  Dans le **Gestionnaire des services Internet (IIS)**, sélectionnez **ServerName**. Dans l' **affichage fonctionnalités**, sélectionnez **certificats de serveur**, cliquez avec le bouton droit, puis sélectionnez Ouvrir la **fonctionnalité**.
    
    <div>
    

    > [!TIP]  
    > Dans l’affichage fonctionnalités des certificats de serveur, si des certificats sont attribués au serveur, ils s’affichent ici. Si un certificat répond à la configuration requise pour le site Web externe dans IIS, vous pouvez le réutiliser. Pour afficher un certificat, cliquez avec le bouton droit sur le certificat, puis sélectionnez <STRONG>afficher.</STRONG>

    
    </div>

4.  Sur le serveur frontal ou le directeur pour lequel vous demandez le certificat, cliquez sur **Démarrer**, sélectionnez **tous les programmes**, **Microsoft Lync Server 2013**, puis cliquez sur **Lync Server Management Shell**.

5.  Dans Lync Server Management Shell, tapez les informations suivantes :
    
        Get-CsCertificate
    
    La sortie est une liste des certificats actuellement sur le serveur dans le magasin de certificats personnels de l’ordinateur. Notez que dans le certificat combiné (autrement dit, les services Web internes et externes par défaut utilisent le même certificat) vous constaterez que la propriété Use sera remplie avec la valeur par défaut, WebServicesInternal et WebServicesExternal. Par ailleurs, la propriété d’empreinte est identique pour chaque type d’utilisation. Un exemple de sortie de Get-CsCertificate est illustré dans cet exemple :
    
    ![Get-CsCertificate informations sur l’état actuel de scert](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate informations sur l’état actuel de scert")

6.  Dans Lync Server Management Shell, tapez les informations suivantes :
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    Où la commande complète s’afficherait comme suit :
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > Par défaut, la requête-CsCertificate remplit le nom du sujet avec le nom du serveur ou du pool et les entrées du nom alternatif du serveur et celles du nom de domaine complet (FQDN) du serveur et les noms de domaine complets des services Web internes et externes. Pour ce faire, elle fait référence au document topologique dans votre déploiement. S’il existe une valeur manquante et que vous avez spécifié le paramètre – Verbose, vous serez averti que les valeurs calculées et réelles d’autres noms sont différentes, mais qu’elle ne vous indique pas quelles valeurs sont manquantes. Elle vous fournit la valeur calculée entière que l’applet de la cmdlet référence. Utilisez la chaîne de noms alternatifs calculés dans la sortie pour demander à nouveau le certificat qui inclura toutes les valeurs.

    
    </div>
    
    ![Sortie d’une demande de certificat à l’aide d’une requête-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Sortie d’une demande de certificat à l’aide d’une requête-CsCertifica")

7.  Dans Lync Server Management Shell, tapez les informations suivantes :
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    Où la commande complète s’afficherait comme suit :
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    La sortie de l’applet de commande Set-CsCertificate indique que le certificat (identifié par l’empreinte numérique du certificat) est attribué à l’utilisation par défaut de WebServicesExternal et WebServicesInternal.
    
    ![Sortie de Set-CsCertificate sur IIS WebEx](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Sortie de Set-CsCertificate sur IIS WebEx")

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a>Pour vérifier ou configurer l’authentification et les certificats dans les répertoires virtuels d’IIS

1.  Cliquez sur **Démarrer**, sur **tous les programmes**, sélectionnez **Outils d’administration**, puis cliquez sur **Gestionnaire des services Internet (IIS)**.

2.  Dans le **Gestionnaire des services Internet (IIS)**, développez **NomServeur**, puis **sites**.

3.  Cliquez avec le bouton droit sur **site Web externe de Lync Server**, puis cliquez sur **modifier les liaisons** .

4.  Vérifiez que https est associé au port 4443, puis cliquez sur **https**.

5.  Sélectionnez l’entrée HTTPs, cliquez sur **modifier**, puis vérifiez que Lync Server WebServicesExternalCertificate est lié à ce protocole. Comparez l’empreinte numérique de l’applet de connexion Set-CsCertificate pour vous assurer que le certificat attendu est associé correctement à la liaison HTTPs.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Get-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

