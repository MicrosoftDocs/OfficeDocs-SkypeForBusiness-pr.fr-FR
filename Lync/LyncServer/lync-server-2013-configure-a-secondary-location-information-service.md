---
title: Configurer un service Informations d’emplacement secondaire
TOCTitle: Configurer un service Informations d’emplacement secondaire
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398138(v=OCS.15)
ms:contentKeyID: 49296173
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurer un service Informations d’emplacement secondaire

 

_**Dernière rubrique modifiée :** 2012-10-30_

Lync Server 2013 comporte une interface de service web qui vous permet de pointer le service d’informations sur l’emplacement vers une base de données SLS (Secondary Location Source, source d’emplacements secondaires). L’interface de service web qui se connecte à la base de données SLS doit être conforme au WSDL (langage de description de services) du service d’informations sur l’emplacement. Si une base de données d’emplacements et une base de données d’emplacements secondaires sont configurées, le service d’informations sur l’emplacement interrogera d’abord la base de données d’emplacements, et si celle-ci ne renvoie aucun résultat, il transmet la demande d’emplacement du client à la base de données SLS. Si l’emplacement existe dans celle-ci, le service d’informations sur l’emplacement transmet l’emplacement au client.

Pour plus d’informations, voir la documentation de Lync Server Management Shell pour l’applet de commande suivante :

  - **Set-CsWebServiceConfiguration**

## Pour configurer la base de données d’emplacements secondaires

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande suivante pour configurer l’URL de l’emplacement de la base de données d’emplacements secondaires.
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>"

