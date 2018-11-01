---
title: "Lync Server 2013 : Créa. des objets de contact pour la mes. un. Exchange héb."
TOCTitle: 'Création des objets de contact pour la messagerie unifiée Exchange hébergée '
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412765(v=OCS.15)
ms:contentKeyID: 49298391
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création des objets de contact pour la messagerie unifiée Exchange hébergée dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-24_

La procédure suivante explique comment créer des objets Contact Standard automatique ou Accès abonné pour la messagerie unifiée Exchange hébergée.

Pour plus d’informations, reportez-vous à [Gestion des objets Contact Exchange hébergés dans Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) dans la documentation de planification.

Pour plus d’informations sur la configuration des objets Contact, reportez-vous à la documentation Lync Server Management Shell pour les applets de commande suivantes :

  - [New-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExUmContact)

  - [Set-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExUmContact)

> [!IMPORTANT]  
> Avant que les objets Contact Lync Server 2013 puissent être activés pour la messagerie unifiée Exchange hébergée, une stratégie de messagerie vocale hébergée qui s’applique à eux doit être déployée. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-hosted-voice-mail-policies.md">Stratégies de messagerie vocale hébergées dans Lync Server 2013</a>.

## Pour créer des objets Contact Standard automatique ou Accès abonné pour la messagerie unifiée Exchange hébergée

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande New-CsExUmContact pour créer les objets Contact requis pour votre déploiement. Exécutez par exemple, la commande suivante pour créer un objet Contact Standard automatique ou Accès abonné :
    
    ```
    New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
    ```
    ```
    New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
    ```
    
    Ces exemples définissent les paramètres suivants :
    
      - **SipAddress** indique l’adresse SIP de l’objet Contact. Cette adresse ne doit pas avoir déjà été utilisée pour configurer un objet Contact ou utilisateur dans les services de domaine Active Directory. Cette valeur doit se trouver au format « sip:\< *SIP address* \> » comme indiqué dans les exemples précédents.
    
      - **RegistrarPool** spécifie le nom de domaine complet du pool sur lequel le service de serveur d’inscriptions est exécuté.
        
        > [!NOTE]  
        > Les objets Contact de la messagerie unifiée Exchange ne peuvent pas être déplacés vers des pools qui font partie de déploiements de Lync Server 2013 antérieurs à Lync Server 2013.    
      - **OU** spécifies l’unité d’organisation Active Directory dans laquelle cet objet Contact sera situé.
    
      - **DisplayNumber** spécifie le numéro de téléphone de l’objet Contact. Le numéro de téléphone de chaque objet Contact doit être unique.
    
      - **AutoAttendant** indique si l’objet Contact est un standard automatique. Le standard automatique fournit un ensemble d’invites vocales qui permettent aux appelants de naviguer dans le système téléphonique et de joindre la personne désirée. Si ce paramètre est défini sur la valeur **False** (par défaut), cela indique un objet Contact Accès abonné.

