---
title: 'Lync Server 2013 : Vérification de l’accès avec le proxy inverse'
TOCTitle: Vérification de l’accès avec le proxy inverse
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429697(v=OCS.15)
ms:contentKeyID: 49296772
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vérification de l’accès avec le proxy inverse dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-03-29_

La procédure suivante vous permet de vérifier que vos utilisateurs peuvent accéder aux informations présentes sur le proxy inverse. Vous devrez peut-être finaliser la configuration du pare-feu et du DNS (Domain Name System) pour que l’accès fonctionne correctement.

## Pour vérifier que vous avez accès au site via Internet

  - Ouvrez un navigateur web et, dans la barre **Adresse**, tapez les URL que les clients utilisent pour accéder aux fichiers de carnet d’adresses et au site web de conférence, comme suit :
    
      - Concernant le serveur de carnet d’adresses, tapez une URL du type : **https://*externalwebfarmFQDN*/abs** où *externalwebfarmFQDN* est le nom de domaine complet des services web externes qui hébergent les services de carnet d’adresses. L’utilisateur doit recevoir une demande d’accès HTTP, car l’authentification Windows par défaut est configurée pour la sécurité du répertoire dans le dossier Serveur de carnet d’adresses.
    
      - Concernant la conférence web, tapez une URL du type : **https://*externalwebfarmFQDN*/meet** où *externalwebfarmFQDN* est le nom de domaine complet de la batterie de serveurs web externe qui héberge le contenu de réunion. Cette URL doit afficher la page d’identification et de résolution des problèmes pour la conférence. Vous pouvez aussi confirmer que votre URL simple pour la conférence fonctionne correctement. Un exemple d’URL simple pour participer à la conférence pourrait être https://meet.contoso.com
    
      - Concernant le développement de groupes de distribution, tapez une URL du type : **https://*externalwebfarmFQDN*/GroupExpansion/service.svc**. L’utilisateur doit recevoir une demande d’accès HTTP, car l’authentification Windows par défaut est configurée pour la sécurité du répertoire dans le service de développement de groupes de distribution.
    
      - Pour rejoindre la conférence, tapez l’URL simple de type **https://*externalwebfarmFQDN* /dialin** où *externalwebfarmFQDN* est le nom de domaine complet de la batterie de serveurs web qui héberge la page de numérotation pour la conférence rendez-vous. L’utilisateur doit être dirigé vers la page de numérotation. Vous pouvez aussi confirmer que votre URL simple de numérotation fonctionne correctement. Un exemple d’URL simple pour la numérotation pourrait être https://dialin.contoso.com
    
      - Pour vérifier le fonctionnement correct de l’URL de découverte automatique, tapez https://lyncdiscover. *externaldomainFQDN* . Le navigateur doit vous inviter à ouvrir un fichier. Sélectionnez le Bloc-notes pour l’ouvrir. Vous recevez une réponse par défaut semblable à la suivante :
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

