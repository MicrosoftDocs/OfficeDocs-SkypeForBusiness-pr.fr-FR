---
title: 'Lync Server 2013 : vérification ou configuration de l’authentification et de la certification sur les répertoires virtuels IIS'
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
ms.openlocfilehash: b4a9e4b2ad53b3fa3a339eae7b4b1ee1f4412548
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a>Vérifier ou configurer l’authentification et la certification sur les répertoires virtuels IIS dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-05-25_

Utilisez la procédure suivante pour configurer le certificat sur vos répertoires virtuels IIS (Internet Information Services) ou vérifier que le certificat est configuré correctement. Effectuez la procédure suivante sur chaque serveur qui exécute les services Internet (IIS) dans votre pool Lync Server interne et dans les serveurs de pools facultatifs Director.

<div>


> [!NOTE]  
> La procédure suivante définit une procédure pour demander un certificat combiné qui est utilisé à des fins telles que Lync Server, le site Web interne et le site Web externe dans les services Internet (IIS). Lync Server 2010 a introduit un ensemble d’applets de&nbsp;commande Windows PowerShell Lync Server Management Shell pour l’objectif de la gestion de la demande de certificat, de l’importation et de l’affectation. La procédure part du principe qu’une autorité de certification capable de traiter la demande a été déployée en interne. Si vous utilisez des certificats publics pour votre serveur Lync Server ou si votre autorité de certification requiert une demande hors connexion, consultez la syntaxe détaillée dans cette rubrique pour plus d’informations sur le paramètre – OUTPUT. <A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a>Pour configurer l’authentification et les certificats au niveau des répertoires virtuels IIS

1.  Pour effectuer correctement les opérations suivantes, vous devez être connecté à l’ordinateur (serveur frontal ou directeur) où les services Web sont installés et être administrateur local. Vous devez disposer des autorisations de **lecture** et d’**inscription** sur l’autorité de certification à laquelle vous demanderez les certificats, si l’autorité de certification est l’autorité de certification de votre organisation. Vous n’avez pas besoin d’autorisations sur l’autorité de certification si vous prévoyez de configurer et d’adresser une demande de certificat hors connexion.

2.  Cliquez sur **Démarrer**, sélectionnez **Tous les programmes**, **Outils d’administration**, puis cliquez sur **Gestionnaire des services Internet (IIS)**.

3.  Dans le **Gestionnaire des services Internet (IIS)**, sélectionnez **NomServeur**. Dans **Affichage des fonctionnalités**, sélectionnez **Certificats de serveur**, cliquez avec le bouton droit, puis sélectionnez **Ouvrir la fonctionnalité**.
    
    <div>
    

    > [!TIP]  
    > Si des certificats sont assignés au serveur, ils figurent parmi les certificats de serveur de l’affichage des fonctionnalités. Si un certificat répond aux conditions requises pour le site web externe dans IIS, vous pouvez réutiliser ce certificat. Pour afficher un certificat, cliquez avec le bouton droit sur le certificat et sélectionnez <STRONG>Afficher…</STRONG>

    
    </div>

4.  Sur le serveur frontal ou directeur pour lequel vous demandez le certificat, cliquez sur **Démarrer**, sélectionnez **tous les programmes**, **Microsoft Lync Server 2013**, puis cliquez sur **Lync Server Management Shell**.

5.  Dans Lync Server Management Shell, tapez ce qui suit :
    
        Get-CsCertificate
    
    Vous obtenez alors la liste des certificats actuellement présents sur le serveur, dans le magasin de certificats personnel de l’ordinateur. À noter que dans le certificat combiné (c’est-à-dire, quand les services web internes et les services web externes par défaut utilisent le même certificat), vous constaterez que la propriété Use affiche les valeurs Default, WebServicesInternal et WebServicesExternal. De même, la propriété Thumbprint a la même valeur pour chaque type Use. Un exemple de résultat de Get-CsCertificate est fourni dans cet exemple :
    
    ![Get-CsCertificate informations sur l’état actuel de scert](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate informations sur l’état actuel de scert")

6.  Dans Lync Server Management Shell, tapez ce qui suit :
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    La commande complète apparaîtra comme dans l’exemple suivant :
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > Par défaut, Request-CsCertificate renseigne le nom du sujet avec le nom du serveur ou du pool et remplit l’autre nom du sujet avec des entrées constituées du nom de domaine complet du serveur, du nom de domaine complet du pool, des noms de domaine complets d’URL simples et des noms de domaine complets des services web interne et externe. Pour cela, l’applet de commande se réfère aux documents de topologie de votre déploiement. S’il manque une valeur et que vous avez spécifié le paramètre –Verbose, elle vous signale que les valeurs calculées et réelles des autres noms sont différentes, mais elle ne vous indique pas la valeur manquante. Elle vous fournit la valeur calculée complète à laquelle l’applet de commande se réfère. Utilisez la chaîne des autres noms calculés figurant dans le résultat pour faire une nouvelle demande de certificat qui comportera toutes les valeurs.

    
    </div>
    
    ![Sortie de la demande de certificat à l’aide de request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Sortie de la demande de certificat à l’aide de request-CsCertifica")

7.  Dans Lync Server Management Shell, tapez ce qui suit :
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    La commande complète apparaîtra comme dans l’exemple suivant :
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    La sortie de l’applet de commande Set-CsCertificate vous montre que le même certificat (identifié par l’empreinte numérique du certificat) est assigné pour l’utilisation de Default, WebServicesExternal et WebServicesInternal.
    
    ![Sortie de Set-CsCertificate sur IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Sortie de Set-CsCertificate sur IIS WebExt")

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a>Pour vérifier ou configurer l’authentification et les certificats au niveau des répertoires virtuels IIS

1.  Cliquez sur **Démarrer**, sélectionnez **Tous les programmes**, **Outils d’administration**, puis cliquez sur **Gestionnaire des services Internet (IIS)**.

2.  Dans le **Gestionnaire des services Internet (IIS)**, développez **ServerName**, puis **sites**.

3.  Cliquez avec le bouton droit sur **Lync Server External Web Site**, puis cliquez sur **Modifier les liaisons**

4.  Vérifiez que https est associé au port 4443, puis cliquez sur **https**.

5.  Sélectionnez l’entrée HTTPs, cliquez sur **modifier**, puis vérifiez que Lync Server WebServicesExternalCertificate est lié à ce protocole. Comparez l’empreinte numérique de l’applet de commande Set-CsCertificate pour vous assurer que le certificat attendu est correctement associé à la liaison HTTPS.

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

