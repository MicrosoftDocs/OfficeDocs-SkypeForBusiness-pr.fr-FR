---
title: Créer des itinéraires inter-région réseau
TOCTitle: Créer des itinéraires inter-région réseau
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398368(v=OCS.15)
ms:contentKeyID: 49297227
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer des itinéraires inter-région réseau

 

_**Dernière rubrique modifiée :** 2012-10-20_

Un *itinéraire inter-région réseau* définit l’itinéraire entre deux régions réseau. Chaque paire de régions réseau dans votre déploiement de contrôle d’admission des appels requiert un itinéraire inter-région réseau. Cela permet à chaque région réseau incluse dans le déploiement d’accéder à toute autre région.

Alors que les liens de région définissent les limitations de bande passante sur les connexions entre les régions, un itinéraire inter-région détermine le chemin lié qu’empruntera la connexion pour aller d’une région à l’autre.

Pour plus d’informations sur l’utilisation des itinéraires inter-région réseau, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :

  - [New-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

Dans l’exemple de topologie, les itinéraires inter-région réseau doivent être définis pour chacune des trois paires de régions : Amérique du Nord/EMEA, EMEA/APAC et Amérique du Nord/APAC.

## Pour créer des itinéraires inter-région réseau à l’aide de Lync Server Management Shell

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande **New-CsNetworkInterRegionRoute** pour définir les itinéraires nécessaires. Par exemple, exécutez :
    
    ```
    New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
    ```
    ```
    New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
    ```
    ```
    New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
    ```
    > [!NOTE]  
    > L’itinéraire inter-région réseau Amérique du Nord/APAC requiert deux liens de région réseau, car il n’existe aucun lien de région réseau direct entre elles.

## Pour créer des itinéraires inter-région réseau à l’aide du Panneau de configuration Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3.  Cliquez sur le bouton de navigation **Itinéraire de région**.

4.  Cliquez sur **Nouveau**.

5.  Dans la page **Nouvel itinéraire de région**, cliquez sur **Nom**, puis tapez un nom pour l’itinéraire inter-région réseau.

6.  Cliquez sur **Région réseau n° 1**, puis cliquez dans la liste sur une région réseau que vous souhaitez acheminer vers la région réseau n° 2.

7.  Cliquez sur **Région réseau n° 2**, puis cliquez dans la liste sur une région réseau que vous souhaitez acheminer vers la région réseau n° 1.

8.  Cliquez sur **Ajouter** en regard du champ **Liens de région réseau**, puis ajoutez un lien de région réseau qui sera utilisé dans l’itinéraire inter-région réseau.
    
    > [!NOTE]  
    > Si vous créez un itinéraire pour deux régions réseau qui n’ont pas de lien de région réseau direct entre elles, vous devez ajouter tous les liens nécessaires pour terminer l’itinéraire. Par exemple, l’itinéraire inter-région réseau Amérique du Nord/APAC requiert deux liens de région réseau, car il n’existe aucun lien de région réseau direct entre elles.

9.  Cliquez sur **Valider**.

10. Pour terminer la création des itinéraires inter-région réseau pour votre topologie, répétez les étapes 4 à 9 en spécifiant les paramètres correspondant à d’autres itinéraires inter-région réseau.

