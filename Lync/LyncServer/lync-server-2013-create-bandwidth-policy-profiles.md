---
title: Créer des profils de stratégie de bande passante dans Lync Server 2013
TOCTitle: Créer des profils de stratégie de bande passante dans Lync Server 2013
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412785(v=OCS.15)
ms:contentKeyID: 49298434
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer des profils de stratégie de bande passante dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-19_

Des *stratégies de bande passante* définissent des restrictions d’utilisation de la bande passante pour des modes audio et vidéo en temps réel. Des stratégies de bande passante sont appliquées à des *profils de stratégie de bande passante* qui peuvent être appliqués à des sites réseau multiples pour le contrôle d’admission des appels.

Pour bénéficier de conseils relatifs aux limites de bande passante que vous devez définir dans votre déploiement CAC, voir [Définition de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) dans la documentation de planification.

Pour plus d’informations sur l’utilisation des stratégies de bande passante et des profils de stratégie, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :

  - [New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

Les stratégies d’exemple créées lors de la procédure suivante définissent des limites pour l’ensemble du trafic audio, les sessions audio individuelles, l’ensemble du trafic vidéo et les sessions vidéo individuelles. Le profil de stratégie de bande passante « 5Mb\_Link » définit par exemple les limites suivantes :

  - Limite audio : 2 000 Kbits/s

  - Limite de session audio : 200 Kbits/s

  - Limite vidéo : 1 400 Kbits/s

  - Limite de session vidéo : 700 Kbits/s

> [!NOTE]  
> La valeur minimum de limite de session audio est 40 Kbits/s La valeur minimum de limite de session vidéo est 100 Kbits/s

## Pour créer des profils de stratégie de bande passante à l’aide de Management Shell

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Pour chaque profil de stratégie de bande passante que vous voulez créer, exécutez l’applet de commande New-CsNetworkBandwidthPolicyProfile. Par exemple, exécutez :
    
    ```
    New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
    ```
    ```
    New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
    ```
    ```
    New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
    ```
    ```
    New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
    ```

## Pour créer des profils de stratégie de bande passante à l’aide du Panneau de configuration Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3.  Cliquez sur le bouton de navigation **Profil de stratégie**.

4.  Cliquez sur **Nouveau**.

5.  A la page **Nouveau profil de stratégie**, cliquez sur **Nom**, puis tapez un nom pour le profil de stratégie de bande passante.

6.  Cliquez sur **Limite audio**, puis tapez le nombre maximum de Kbits/s à autoriser pour toutes les sessions audio combinées.

7.  Cliquez sur **Limite de session audio**, puis tapez le nombre maximum de Kbits/s à autoriser pour chaque session audio individuelle.

8.  Cliquez sur **Limite vidéo**, puis tapez le nombre maximum de Kbits/s à autoriser pour toutes les sessions vidéo combinées.

9.  Cliquez sur **Limite de session vidéo**, puis tapez le nombre maximum de Kbits/s à autoriser pour chaque session vidéo individuelle.

10. En option, cliquez sur **Description**, puis tapez des informations supplémentaires pour décrire ce profil de stratégie de bande passante.

11. Cliquez sur **Valider**.

12. Pour finir de créer des profils de stratégie de bande passante pour votre topologie, répétez les étapes 4 à 11 avec des paramètres pour d’autres profils de stratégie de bande passante.

