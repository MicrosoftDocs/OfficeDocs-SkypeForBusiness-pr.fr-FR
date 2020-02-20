---
title: 'Lync Server 2013 : associer un sous-réseau à un site réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate a subnet with a network site
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48185043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 419c88e32e3a0dd78fdc2503dcc2bb09b2c705ac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a>Associer un sous-réseau à un site réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Chaque sous-réseau de votre réseau doit être associé à un site réseau spécifique, car les informations de sous-réseau servent à définir le site réseau sur lequel figure un système d’extrémité lorsqu’une nouvelle session est initiée. Lorsque l’emplacement de chaque partie d’une session est connu, les fonctionnalités avancées de voix entreprise peuvent appliquer ces informations pour déterminer comment gérer la configuration de l’appel ou le routage.

<div>


> [!IMPORTANT]  
> Toutes les adresses IP publiques configurées des serveurs Edge audio/vidéo de votre déploiement doivent être ajoutées à vos paramètres de configuration réseau. Ces adresses IP sont ajoutées sous forme de sous-réseaux avec un masque de 32. Le site réseau associé doit correspondre au site réseau configuré approprié. Par exemple, l’adresse IP publique correspondant au serveur Edge A/V du site central Chicago serait NetworkSiteID Chicago. Pour plus d’informations sur les adresses IP publiques, voir <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">determine External A/V Firewall and Port Requirements for Lync Server 2013</A> dans la documentation de planification.



</div>

<div>


> [!NOTE]  
> Une alerte d’indicateur d’intégrité clé est générée, indiquant une liste d’adresses IP figurant dans votre réseau, mais non associées à un sous-réseau ou figurant dans un sous-réseau non associé à un site réseau. L’alerte n’est générée qu’une seule fois par période de huit heures. Les informations d’alerte pertinentes et un exemple sont présentés ci-dessous :<BR><STRONG>Source :</STRONG> Service de stratégie de bande passante CS (Core)<BR><STRONG>Numéro d’événement :</STRONG> 36034<BR><STRONG>Niveau :</STRONG> 2<BR><STRONG>Description :</STRONG> Les sous-réseaux pour les adresses IP suivantes &lt;: la liste des&gt; adresses IP n’est pas configurée ou les sous-réseaux ne sont pas associés à un site réseau.<BR><STRONG>Cause :</STRONG> Les sous-réseaux pour les adresses IP correspondantes sont absents des paramètres de configuration du réseau ou les sous-réseaux ne sont pas associés à un site réseau.<BR><STRONG>Résolution :</STRONG> Ajoutez des sous-réseaux correspondant à la liste des adresses IP dans les paramètres de configuration du réseau et associez chaque sous-réseau à un site réseau.<BR>Par exemple, si la liste d’adresses IP qui apparaît dans l’alerte indique 10.121.248.226 et 10.121.249.20, soit ces adresses IP ne sont pas associées à un sous-réseau, soit le sous-réseau auquel elles sont associées n’appartient pas au site réseau. Si 10.121.248.0/24 et 10.121.249.0/24 sont les sous-réseaux associés à ces adresses, vous pouvez résoudre le problème comme suit : 
> <OL>
> <LI>
> <P>Vérifiez que l’adresse IP 10.121.248.226 est associée au sous-réseau 10.121.248.0/24 et l’adresse IP 10.121.249.20 au sous-réseau 10.121.249.0/24.</P>
> <LI>
> <P>Vérifiez que les sous-réseaux 10.121.248.0/24 et 10.121.249.0/24 sont chacun associés à un site réseau.</P></LI></OL>



</div>

Pour plus d’informations sur l’utilisation des sous-réseaux, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :

  - [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> Si vous utilisez un grand nombre de sous-réseaux, nous vous recommandons d’utiliser un fichier de valeurs séparées par des virgules (CSV) pour associer les sous-réseaux à des sites. Le fichier CSV doit comporter les quatre colonnes suivantes : <STRONG>adresse IP</STRONG>, <STRONG>masque</STRONG>, <STRONG>description</STRONG>, <STRONG>ID de site réseau</STRONG>.



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a>Pour associer un sous-réseau à un site réseau à l’aide de Management Shell

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande **New-CsNetworkSubnet** pour associer un sous-réseau à un site réseau :
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    Par exemple :
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    Dans cet exemple, vous avez créé une association entre le sous-réseau 172.11.12.13 et le site réseau « Chicago ».

3.  Répétez l’étape 2 pour tous les sous-réseaux de votre topologie.

</div>

<div>

## <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>Pour associer des sous-réseaux à des sites réseau en important un fichier CSV

1.  Créez un fichier CSV incluant tous les sous-réseaux que vous souhaitez ajouter. Par exemple, créez un fichier **subnet.csv** avec le contenu suivant :
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Exécutez l’applet de commande suivante pour importer le fichier **subnet. csv**, puis enregistrez son contenu dans le magasin de gestion Lync Server :
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a>Pour associer un sous-réseau à un site réseau à l’aide du Panneau de configuration Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3.  Cliquez sur le bouton de navigation **Sous-réseau**.

4.  Cliquez sur **Nouveau**.

5.  Dans la page **Nouveau sous-réseau**, cliquez sur **ID de sous-réseau**, puis entrez la première adresse de la plage d’adresses IP définie par le sous-réseau que vous souhaitez associer à un site réseau.

6.  Cliquez sur **Masque**, puis entrez le masque de bits à appliquer au sous-réseau.

7.  Cliquez sur **ID de site réseau**, puis sélectionnez l’ID du site auquel vous ajoutez ce sous-réseau.
    
    <div>
    

    > [!NOTE]  
    > Si vous n’avez pas encore créé de sites réseau, cette liste est vide. Pour plus d’informations sur la procédure, voir <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or Modify a Network site in Lync Server 2013</A>. Vous pouvez également récupérer des ID de site pour votre déploiement en exécutant l’applet de commande <STRONG>Get-CsNetworkSite</STRONG>. Pour plus d’informations, voir la documentation Lync Server Management Shell.

    
    </div>

8.  Éventuellement, cliquez sur **Description**, puis entrez des informations supplémentaires pour décrire ce sous-réseau.

9.  Cliquez sur **Valider**.

Répétez ces étapes pour ajouter d’autres sous-réseaux à un site réseau.

</div>

</div>

<span> </span>

</div>

</div>

</div>

