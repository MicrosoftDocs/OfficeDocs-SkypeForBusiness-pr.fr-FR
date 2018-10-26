---
title: 'Lync Server 2013 : Association d’un sous-réseau à un site réseau'
TOCTitle: Association d’un sous-réseau à un site réseau
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412804(v=OCS.15)
ms:contentKeyID: 49298507
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Association d’un sous-réseau à un site réseau dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-10-20_

Chaque sous-réseau de votre réseau doit être associé à un site réseau spécifique, car les informations de sous-réseau servent à définir le site réseau sur lequel figure un point de terminaison lorsqu’une nouvelle session est initiée. Quand l’emplacement de chaque partie d’une session est déterminé, les fonctionnalités Voix Entreprise avancées peuvent appliquer ces informations pour définir la façon de gérer la configuration et le routage des appels.

> [!IMPORTANT]  
> Toutes les adresses IP publiques configurées des serveurs Edge audio/vidéo de votre déploiement doivent être ajoutées à vos paramètres de configuration réseau. Ces adresses IP sont ajoutées sous forme de sous-réseaux avec un masque de 32. Le site réseau associé doit correspondre au site réseau configuré approprié. Par exemple, l’adresse IP publique correspondant au serveur Edge A/V du site central Chicago serait NetworkSiteID Chicago. Pour plus d’informations sur les adresses IP publiques, reportez-vous à <a href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013</a> dans la documentation de planification.

> [!NOTE]  
> Une alerte d’indicateur d’intégrité clé est générée, indiquant une liste d’adresses IP figurant dans votre réseau, mais non associées à un sous-réseau ou figurant dans un sous-réseau non associé à un site réseau. L’alerte n’est générée qu’une seule fois par période de huit heures. Les informations d’alerte pertinentes et un exemple sont présentés ci-dessous :<br />
<strong>Source</strong> : Service de stratégie de bande passante (principal) CS<br />
<strong>Numéro d’événement</strong> : 36034<br />
<strong>Niveau</strong> : 2<br />
<strong>Description</strong> : les sous-réseaux pour les adresses IP suivantes : &lt;liste des adresses IP&gt; ne sont pas configurés ou les sous-réseaux ne sont pas associés à un site réseau<br />
<strong>Cause</strong> : les sous-réseaux pour les adresses IP correspondantes sont absents des paramètres de configuration du réseau ou les sous-réseaux ne sont pas associés à un site réseau.<br />
<strong>Résolution</strong> : ajoutez aux paramètres de configuration réseau les sous-réseaux correspondant à la liste des adresses IP et associez chaque sous-réseau à un site réseau.<br />
Par exemple, si la liste d’adresses IP qui s’affiche dans l’alerte indique 10.121.248.226 et 10.121.249.20, soit ces adresses IP ne sont pas associées à un sous-réseau, soit le sous-réseau auquel elles sont associées n’appartient pas au site réseau. Si 10.121.248.0/24 et 10.121.249.0/24 sont les sous-réseaux associés à ces adresses, vous pouvez résoudre le problème comme suit :<ol>
> <li><p>Vérifiez que l’adresse IP 10.121.248.226 est associée au sous-réseau 10.121.248.0/24 et l’adresse IP 10.121.249.20 au sous-réseau 10.121.249.0/24.</p></li>
> <li><p>Vérifiez que les sous-réseaux 10.121.248.0/24 et 10.121.249.0/24 sont chacun associés à un site réseau.</p></li></ol>


Pour plus d’informations sur l’utilisation des sous-réseaux, reportez-vous à la documentation de Lync Server Management Shell pour les applets de commande suivantes :

  - [New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet)

  - [Get-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSubnet)

  - [Set-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkSubnet)

  - [Remove-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkSubnet)

> [!TIP]  
> Si vous utilisez un grand nombre de sous-réseaux, nous vous recommandons d’utiliser un fichier de valeurs séparées par des virgules (CSV) pour associer les sous-réseaux à des sites. Le fichier CSV doit comporter les quatre colonnes suivantes : <strong>adresse IP</strong>, <strong>masque</strong>, <strong>description</strong>, <strong>ID de site réseau</strong>.

## Pour associer un sous-réseau à un site réseau à l’aide de Management Shell

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande **New-CsNetworkSubnet** pour associer un sous-réseau à un site réseau :
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    Exemple :
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    Dans cet exemple, vous avez créé une association entre le sous-réseau 172.11.12.13 et le site réseau « Chicago ».

3.  Répétez l’étape 2 pour tous les sous-réseaux de votre topologie.

## Pour associer des sous-réseaux à des sites réseau en important un fichier CSV

1.  Créez un fichier CSV incluant tous les sous-réseaux que vous souhaitez ajouter. Par exemple, créez un fichier **subnet.csv** avec le contenu suivant :
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez l’applet de commande suivante pour importer le fichier **subnet.csv**, puis enregistrez son contenu dans le magasin de gestion Lync Server :
    
        import-csv subnet.csv | foreach {New-CsNetworkSubnet $_IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

## Pour associer un sous-réseau à un site réseau à l’aide du Panneau de configuration Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau** .

3.  Cliquez sur le bouton de navigation **Sous-réseau** .

4.  Cliquez sur **Nouveau** .

5.  Dans la page **Nouveau sous-réseau** , cliquez sur **ID de sous-réseau** , puis entrez la première adresse de la plage d’adresses IP définie par le sous-réseau que vous souhaitez associer à un site réseau.

6.  Cliquez sur **Masque** , puis entrez le masque de bits à appliquer au sous-réseau.

7.  Cliquez sur **ID de site réseau** , puis sélectionnez l’ID du site auquel vous ajoutez ce sous-réseau.
    
    > [!NOTE]  
    > Si vous n’avez pas encore créé de sites réseau, cette liste est vide. Pour plus d’informations sur la procédure, reportez-vous à <a href="lync-server-2013-create-or-modify-a-network-site.md">Création ou modification d’un site réseau dans Lync Server 2013</a>. Vous pouvez également récupérer des ID de site pour votre déploiement en exécutant l’applet de commande <strong>Get-CsNetworkSite</strong>. Pour plus d’informations, reportez-vous à la documentation relative à Lync Server Management Shell.

8.  Éventuellement, cliquez sur **Description** , puis entrez des informations supplémentaires pour décrire ce sous-réseau.

9.  Cliquez sur **Valider** .

Répétez ces étapes pour ajouter d’autres sous-réseaux à un site réseau.

