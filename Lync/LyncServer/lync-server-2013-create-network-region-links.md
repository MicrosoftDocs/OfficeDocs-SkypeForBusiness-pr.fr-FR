---
title: Créer des liens de région réseau
TOCTitle: Créer des liens de région réseau
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg413047(v=OCS.15)
ms:contentKeyID: 49299402
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer des liens de région réseau

 

_**Dernière rubrique modifiée :** 2012-10-19_

Au sein d’un réseau, les régions sont liées par une connectivité au réseau étendu physique. Un *lien de région réseau* crée un lien entre deux régions configurées pour le contrôle d’admission des appels et définit les restrictions de bande passante sur le trafic audio et vidéo entre ces régions.

Pour plus d’informations sur l’utilisation des liens de région réseau, voir la documentation Lync Server Management Shell pour les applets de commande suivantes :

  - [New-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegionLink)

  - [Get-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkRegionLink)

  - [Remove-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkRegionLink)

L’exemple de topologie possède un lien entre les régions Amérique du Nord et APAC et un lien entre les régions EMEA et APAC. Chacun de ces liens de région est contraint par une bande passante de réseau étendu, tel que décrit dans le tableau Informations sur la bande passante de lien de région dans la section [Exemple : collecte des données de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) de la documentation de planification.

## Pour créer des liens de région de réseau à l’aide de Lync Server Management Shell

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande New-CsNetworkRegionLink pour créer des liens de région et appliquer des profils de stratégie de bande passante appropriés. Par exemple, exécutez :
    
    ```
    New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
    ```
    ```
    New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
    ```

## Pour créer des liens de région de réseau à l’aide du Panneau de configuration Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3.  Cliquez sur le bouton de navigation **Lien de région**.

4.  Cliquez sur **Nouveau**.

5.  Sur la page **Nouveau lien de région**, cliquez sur **Nom**, puis tapez le nom du lien de région réseau.

6.  Cliquez sur **Région réseau n° 1**, puis sur la région réseau dans la liste que vous voulez lier à la Région réseau n° 2.

7.  Cliquez sur **Région réseau n° 2**, puis sur la région réseau dans la liste que vous voulez lier à la Région réseau n° 1.

8.  Si vous le souhaitez, vous pouvez cliquer sur **Stratégie de bande passante**, puis sélectionner le profil de stratégie de bande passante que vous souhaitez appliquer au lien de région réseau.
    
    > [!NOTE]  
    > Appliquez une stratégie de bande passante uniquement si le lien de région réseau est contraint par la bande passante et que vous souhaitez utiliser le contrôle d’admission des appels pour contrôler le trafic multimédia sur ce lien.

9.  Cliquez sur **Valider**.

10. Pour finir de créer des liens région réseau pour votre topologie, répétez les étapes 4 à 9 avec les paramètres d’autres régions.

