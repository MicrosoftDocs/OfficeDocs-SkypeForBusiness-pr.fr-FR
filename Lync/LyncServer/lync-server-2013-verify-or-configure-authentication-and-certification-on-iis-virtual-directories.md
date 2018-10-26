---
title: "LS 2013 : Vér./conf. auth. et certif. dans les rép. virt. des serv. Int. (IIS)"
TOCTitle: Vérification ou configuration de l’authentification et de la certification dans les répertoires virtuels des services Internet (IIS)
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429702(v=OCS.15)
ms:contentKeyID: 49296951
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Connexion d’un Survivable Branch Appliance à un pool de serveurs frontaux

 

_**Dernière rubrique modifiée :** 2012-05-25_

Utilisez la procédure suivante pour configurer le certificat sur vos répertoires virtuels des services Internet (IIS) ou pour vérifier que le certificat est correctement configuré. Effectuez la procédure suivante sur chaque serveur exécutant les services Internet (IIS) dans votre pool Lync Server interne et les serveurs directeur ou de pool de directeurs facultatifs.

> [!NOTE]  
> La procédure suivante vise à faire une demande de certificat combiné polyvalent pour Lync Server, le site web interne et le site web externe dans les services Internet (IIS). Lync Server 2010 a inauguré un jeu d’applets de commande Windows PowerShellLync Server Management Shell à des fins expresses de gestion de la demande, de l’importation et de l’affectation de certificats. La procédure part du principe qu’une autorité de certification capable de traiter la demande a été déployée en interne. Si vous utilisez des certificats publics pour vos besoins Lync Server ou si votre autorité de certification impose une demande hors connexion, examinez la syntaxe détaillée dans cette rubrique pour plus d’informations sur le paramètre –Output . <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</a>

## Pour configurer l’authentification et les certificats au niveau des répertoires virtuels des services Internet (IIS)

1.  Pour mener à bien la procédure suivante, vous devez être connecté sur l’ordinateur (serveur frontal ou directeur) où sont installés les services web et être administrateur local. Vous devez disposer des autorisations de **lecture** et d’**inscription** sur l’autorité de certification à laquelle vous demanderez les certificats, si l’autorité de certification est l’autorité de certification de votre organisation. Vous n’avez pas besoin d’autorisations sur l’autorité de certification si vous prévoyez de configurer et d’adresser une demande de certificat hors connexion.

2.  Cliquez sur **Démarrer** , sélectionnez **Tous les programmes** , **Outils d’administration** , puis cliquez sur **Gestionnaire des services Internet (IIS)** .

3.  Dans le **Gestionnaire des services Internet (IIS)** , sélectionnez **NomServeur** . Dans **Affichage des fonctionnalités** , sélectionnez **Certificats de serveur** , cliquez avec le bouton droit, puis sélectionnez **Ouvrir la fonctionnalité** .
    
    > [!TIP]  
    > Si des certificats sont affectés au serveur, ils figurent parmi les certificats de serveur de l’affichage des fonctionnalités. Si un certificat répond aux conditions requises pour le site web externe dans les services Internet (IIS), vous pouvez réutiliser ce certificat. Pour afficher un certificat, cliquez avec le bouton droit sur le certificat et sélectionnez <strong>Afficher…</strong>

4.  Sur le serveur frontal ou le directeur pour lequel vous demandez le certificat, cliquez sur **Démarrer** , sélectionnez **Tous les programmes** , **Microsoft Lync Server 2013**, puis cliquez sur **Lync Server Management Shell**.

5.  Dans Lync Server Management Shell, tapez ce qui suit :
    
        Get-CsCertificate
    
    Vous obtenez alors la liste des certificats actuellement présents sur le serveur, dans le magasin de certificats personnel de l’ordinateur. À noter que dans le certificat combiné (c’est-à-dire, quand les services web internes et les services web externes par défaut utilisent le même certificat), vous constaterez que la propriété Use affiche les valeurs Default, WebServicesInternal et WebServicesExternal. De même, la propriété Thumbprint a la même valeur pour chaque type Use. Un exemple de résultat de Get-CsCertificate est fourni dans cet exemple :
    
    ![Info Get-CsCertificate sur le statut scert actuel](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Info Get-CsCertificate sur le statut scert actuel")

6.  Dans Lync Server Management Shell, tapez ce qui suit :
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    La commande complète s’affichera comme dans l’exemple suivant :
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    > [!TIP]  
    > Par défaut, Request-CsCertificate renseigne le nom du sujet avec le nom du serveur ou du pool et remplit l’autre nom du sujet avec des entrées constituées du nom de domaine complet du serveur, du nom de domaine complet du pool, des noms de domaine complets d’URL simples et des noms de domaine complets des services web interne et externe. Pour cela, l’applet de commande se réfère aux documents de topologie de votre déploiement. S’il manque une valeur et que vous avez spécifié le paramètre –Verbose, elle vous signale que les valeurs calculées et réelles des autres noms sont différentes, mais elle ne vous indique pas la valeur manquante. Elle vous fournit la valeur calculée complète à laquelle l’applet de commande se réfère. Utilisez la chaîne desautres noms calculés figurant dans le résultat pour faire une nouvelle demande de certificat qui comportera toutes les valeurs.    
    ![Sortie de la demande cert à l’aide de Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Sortie de la demande cert à l’aide de Request-CsCertifica")

7.  Dans Lync Server Management Shell, tapez ce qui suit :
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    La commande complète s’affichera comme dans l’exemple suivant :
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    La sortie de l’applet de commande Set-CsCertificate vous montre que le même certificat (identifié par l’empreinte numérique du certificat) est affecté pour l’utilisation de Default, WebServicesExternal et WebServicesInternal.
    
    ![Sortie de Set-CsCertificate sur IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Sortie de Set-CsCertificate sur IIS WebExt")

## Pour vérifier ou configurer l’authentification et les certificats au niveau des répertoires virtuels des services Internet (IIS)

1.  Cliquez sur **Démarrer** , sélectionnez **Tous les programmes** , **Outils d’administration** , puis cliquez sur **Gestionnaire des services Internet (IIS)** .

2.  Dans le **Gestionnaire de services Internet (IIS)** , développez **nom\_serveur** , puis **Sites** .

3.  Cliquez avec le bouton droit sur **Lync Server External Web Site** , puis cliquez sur **Modifier les liaisons**

4.  Vérifiez que https est associé au port 4443, puis cliquez sur **https** .

5.  Sélectionnez l’entrée HTTPS, cliquez sur **Modifier** , puis vérifiez que le certificat WebServicesExternalCertificate de Lync Server est lié à ce protocole. Comparez l’empreinte numérique de l’applet de commande Set-CsCertificate pour vous assurer que le certificat attendu est correctement associé à la liaison HTTPS.

## Voir aussi

#### Autres ressources

[Get-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate)

