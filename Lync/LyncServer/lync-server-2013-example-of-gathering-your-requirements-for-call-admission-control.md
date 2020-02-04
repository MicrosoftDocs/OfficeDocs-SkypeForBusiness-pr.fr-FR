---
title: Exemple de rassemblement de vos exigences de contrôle d’admission des appels
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Example of gathering your requirements for call admission control
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48183820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 345f5d7e41dd9da3e6d68c59ce9656d3052c57b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a>Exemple : rassemblement de vos exigences de contrôle d’admission des appels dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Cet exemple indique comment planifier et implémenter le contrôle d’admission des appels (CAC). Globalement, il s’agit des activités suivantes :

1.  Identifiez l’ensemble de vos concentrateurs réseau et dorsales principales (connues aussi sous le nom de *régions réseau*).

2.  Identifiez le site Lync Server central qui peut gérer le CAC pour chaque région du réseau.

3.  Identifiez et définissez les *sites réseau* connectés à chaque région réseau.

4.  Pour chaque site réseau pour lequel la connexion au réseau étendu (WAN) est soumise à une bande passante, décrivez la capacité de bande passante de la connexion WAN et les limites de bande passante que l’administrateur réseau a configurées pour le trafic multimédia serveur Lync, le cas échéant. Il n’est pas nécessaire d’inclure les sites dont la bande passante de connexion de réseau étendu n’est pas limitée.

5.  Associez chaque sous-réseau de votre réseau à un site réseau.

6.  Mappez les liaisons entre régions réseau. Pour chaque lien, décrivez la capacité de la bande passante et les limites que l’administrateur réseau a placées sur le trafic multimédia de Lync Server.

7.  Définissez un itinéraire entre chaque paire de régions réseau.

<div>

## <a name="gather-the-required-information"></a>Rassembler les informations requises

Pour préparer le contrôle d’admission des appels, rassemblez les informations présentées dans les étapes suivantes :

1.  Identifiez vos régions réseau. Une région réseau représente une dorsale principale ou un concentrateur réseau.
    
    Une dorsale principale ou un concentrateur réseau fait partie de l’infrastructure réseau informatique qui interconnecte différents éléments du réseau, fournissant ainsi un chemin pour l’échange des informations entre différents réseaux locaux (LAN) ou sous-réseaux. Une dorsale principale peut lier divers réseaux d’un petit emplacement à une zone géographique étendue. La capacité de la dorsale principale est généralement plus grande que celle des réseaux qui s’y connectent.
    
    Notre exemple de topologie comporte trois régions réseau : Amérique du Nord, EMEA et APAC. Une région réseau contient une collection de sites réseau. Définissez les régions réseau de votre entreprise avec l’administrateur réseau.

2.  Identifiez le site central associé à chaque région réseau. Un site central comporte au moins un serveur frontal et est le déploiement du serveur Lync qui gère le CAC pour l’ensemble du trafic multimédia transmis par le biais de la connexion WAN de la région du réseau.
    
    **Exemple de réseau d’entreprise divisé en trois régions réseau**
    
    ![Exemple de topologie réseau avec 3 régions réseau](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Exemple de topologie réseau avec 3 régions réseau")  
    
    <div>
    

    > [!NOTE]
    > Un réseau MPLS (Multiprotocol Label Switching) devrait être représenté en tant que région réseau dans laquelle un emplacement géographique est associé à un site réseau correspondant. Pour plus d’informations, reportez-vous à la rubrique «<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">contrôle d’admission des appels sur un réseau MPLS avec Lync Server 2013</A>» dans la documentation de planification.

    
    </div>
    
    Dans la topologie de réseau de l’exemple précédent, il existe trois régions réseau, chacune avec un site Lync Server central qui gère le CAC. Le site central approprié pour une région de réseau est choisi par le voisinage géographique. Dans la mesure où le trafic multimédia sera le plus lourd dans les régions du réseau, la propriété de l’élément géographique voisin le rend autonome et restera opérationnel même si d’autres sites centraux deviennent indisponibles.
    
    Dans cet exemple, un déploiement de Lync Server appelé Chicago est le site central pour la région Amérique du Nord.
    
    Tous les utilisateurs Lync en Amérique du Nord sont hébergés sur des serveurs dans le déploiement de Chicago. Le tableau ci-dessous répertorie les sites centraux pour les trois régions réseau.
    
    ### <a name="network-regions-and-their-associated-central-sites"></a>Régions réseau et leur site central associé
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Région réseau</th>
    <th>Site central</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Amérique du Nord</p></td>
    <td><p>Chicago</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA</p></td>
    <td><p>Londres</p></td>
    </tr>
    <tr class="odd">
    <td><p>APAC</p></td>
    <td><p>Pékin</p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > Selon la topologie de votre serveur Lync, le même site central peut être attribué à plusieurs zones du réseau.

    
    </div>

3.  Pour chaque région réseau, identifiez tous les sites réseau (bureaux ou emplacements) dont les connexions au réseau étendu ne sont pas soumises à une limite de bande passante. Comme ces sites disposent de liaisons réseau dont la bande passante n’est pas limitée, il n’est pas nécessaire de leur appliquer des stratégies de bande passante CAC.
    
    Dans l’exemple présenté dans le tableau suivant, trois sites réseau disposent de liaisons réseau dont la bande passante n’est pas limitée : New York, Chicago et Détroit.
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a>Sites réseau non limités par la bande passante de la connexion de réseau étendu
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Site réseau</th>
    <th>Région réseau</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>New York</p></td>
    <td><p>Amérique du Nord</p></td>
    </tr>
    <tr class="even">
    <td><p>Chicago</p></td>
    <td><p>Amérique du Nord</p></td>
    </tr>
    <tr class="odd">
    <td><p>Detroit</p></td>
    <td><p>Amérique du Nord</p></td>
    </tr>
    </tbody>
    </table>


4.  Pour chaque région réseau, identifiez tous les sites réseau se connectant à la région réseau via des liaisons de réseau étendu dont la bande passante est limitée.
    
    Pour garantir la qualité de l’audio et de la vidéo, nous recommandons de surveiller les réseaux de réseau étendu des sites dont la bande passante est limitée et d’imposer des stratégies de bande passante CAC limitant le flux multimédia (vocal ou vidéo) à partir de et vers la région réseau.
    
    Dans l’exemple présenté dans le tableau suivant, trois sites réseaux sont limités par la bande passante du réseau étendu : Portland, Reno et Albuquerque.
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a>Sites réseau limités par la bande passante de la connexion de réseau étendu
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Site réseau</th>
    <th>Région réseau</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Albuquerque</p></td>
    <td><p>Amérique du Nord</p></td>
    </tr>
    <tr class="even">
    <td><p>Reno</p></td>
    <td><p>Amérique du Nord</p></td>
    </tr>
    <tr class="odd">
    <td><p>Portland</p></td>
    <td><p>Amérique du Nord</p></td>
    </tr>
    </tbody>
    </table>
    
    **Région réseau CAC Amérique du Nord et trois sites réseau non limités par la bande passante (Chicago, New York et Détroit) et trois sites réseau limités par la bande passante de la liaison de réseau étendu (Portland, Reno et Albuquerque)**
    
    ![Exemples de sites réseau limités par la bande passante de la connexion WAN](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Exemples de sites réseau limités par la bande passante de la connexion WAN")  

5.  Pour chaque liaison de réseau étendu dont la bande passante est limitée, déterminez les points suivants :
    
      - Limite de bande passante globale à appliquer à toutes les sessions audio simultanées. Si une nouvelle session audio entraîne la dépassement de cette limite, Lync Server ne permet pas à la session de démarrer.
    
      - Limite de bande passante à appliquer à chaque session audio individuelle. La bande passante CAC par défaut est de 175 Kbits/s, mais elle est modifiable par l’administrateur.
    
      - Limite de bande passante globale à appliquer à toutes les sessions vidéo simultanées. Si une nouvelle session vidéo ne peut pas être dépassée, Lync Server n’autorise pas le démarrage de la session.
    
      - Limite de bande passante à appliquer à chaque session vidéo individuelle. La bande passante CAC par défaut est de 700 Kbits/s, mais elle est modifiable par l’administrateur.
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a>Sites réseau et informations de restriction de bande passante de réseau étendu (bande passante en Kbits/s)
    
    <table style="width:100%;">
    <colgroup>
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Site réseau</th>
    <th>Région réseau</th>
    <th>Limite BP</th>
    <th>Limite audio</th>
    <th>Limite de session audio</th>
    <th>Limite vidéo</th>
    <th>Limite de session vidéo</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Albuquerque</p></td>
    <td><p>Amérique du Nord</p></td>
    <td><p>5 000</p></td>
    <td><p>2 000</p></td>
    <td><p>175</p></td>
    <td><p>1 400</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>Reno</p></td>
    <td><p>Amérique du Nord</p></td>
    <td><p>10 000</p></td>
    <td><p>4 000</p></td>
    <td><p>175</p></td>
    <td><p>2 800</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="odd">
    <td><p>Portland</p></td>
    <td><p>Amérique du Nord</p></td>
    <td><p>5 000</p></td>
    <td><p>4 000</p></td>
    <td><p>175</p></td>
    <td><p>2 800</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>New York</p></td>
    <td><p>Amérique du Nord</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    </tr>
    <tr class="odd">
    <td><p>Chicago</p></td>
    <td><p>Amérique du Nord</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    </tr>
    <tr class="even">
    <td><p>Detroit</p></td>
    <td><p>Amérique du Nord</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    </tr>
    </tbody>
    </table>


6.  Pour chaque sous-réseau du réseau, indiquez son site réseau associé.
    
    <div>
    

    > [!IMPORTANT]
    > Chaque sous-réseau doit être associé à un site réseau, même si le site réseau n’est pas soumis à une limite de bande passante. Cela est dû au fait que le contrôle d’admission des appels utilise les informations relatives aux sous-réseaux pour déterminer sur quel site réseau un point de terminaison doit se situer. Lorsque les emplacements de chaque partie de la session sont déterminés, le contrôle d’admission des appels peut déterminer si la bande passante est suffisante pour établir l’appel. Lorsqu’une session est établie sur une liaison dont la bande passante n’est pas limitée, une alerte est générée.<BR>Si vous déployez des serveurs Edge A/V, les adresses IP publiques de chaque serveur Edge doivent être associées au site réseau sur lequel le serveur Edge est déployé. Vous devez ajouter chaque adresse IP publique du serveur Edge A/V à vos paramètres de configuration réseau en tant que sous-réseau avec un masque de sous réseau de 32. Par exemple, si vous déployez des serveurs Edge A/V à Chicago, pour chaque adresse IP externe de ces serveurs, créez un sous-réseau avec un masque de sous-réseau de 32 et associez le site réseau Chicago à ces sous-réseaux. Pour plus d’informations sur les adresses IP publiques, voir <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">déterminer la configuration requise pour le pare-feu A/V pour Lync Server 2013</A> dans la documentation de planification.

    
    </div>
    
    <div>
    

    > [!NOTE]
    > Une alerte d’indicateur d’intégrité clé est générée, indiquant une liste d’adresses IP figurant dans votre réseau, mais non associées à un sous-réseau ou figurant dans un sous-réseau non associé à un site réseau. L’alerte n’est générée qu’une seule fois par période de 8 heures. Les informations d’alerte pertinentes et un exemple sont présentés ci-dessous :<BR><STRONG>Source :</STRONG> Service de stratégie de bande passante CS (noyau)<BR><STRONG>Numéro de l’événement :</STRONG> 36034<BR><STRONG>Niveau :</STRONG> 2<BR><STRONG>Description :</STRONG> Les sous-réseaux pour les adresses IP suivantes &lt;: une liste d'&gt; adresses IP n’est pas configurée ou les sous-réseaux ne sont pas associés à un site réseau.<BR><STRONG>Cause :</STRONG> Les sous-réseaux pour les adresses IP correspondantes n’apparaissent pas dans les paramètres de configuration du réseau ou les sous-réseaux ne sont pas associés à un site réseau.<BR><STRONG>Résolution :</STRONG> Ajoutez des sous-réseaux correspondant à la liste précédente d’adresses IP dans les paramètres de configuration du réseau et associez chaque sous-réseau à un site réseau.<BR>Par exemple, si la liste d’adresses IP qui s’affiche dans l’alerte indique 10.121.248.226 et 10.121.249.20, soit ces adresses IP ne sont pas associées à un sous-réseau, soit le sous-réseau auquel elles sont associées n’appartient pas au site réseau. Si 10.121.248.0/24 et 10.121.249.0/24 sont les sous-réseaux associés à ces adresses, vous pouvez résoudre le problème comme suit : 
    > <OL>
    > <LI>
    > <P>Vérifiez que l’adresse IP 10.121.248.226 est associée au sous-réseau 10.121.248.0/24 et l’adresse IP 10.121.249.20 au sous-réseau 10.121.249.0/24.</P>
    > <LI>
    > <P>Vérifiez que les sous-réseaux 10.121.248.0/24 et 10.121.249.0/24 sont chacun associés à un site réseau.</P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a>Sites réseau et sous-réseaux associés (bande passante en Kbits/s)
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Site réseau</th>
    <th>Région réseau</th>
    <th>Limite BP</th>
    <th>Limite audio</th>
    <th>Limite de session audio</th>
    <th>Limite vidéo</th>
    <th>Limite de session vidéo</th>
    <th>Sous-réseaux</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Albuquerque</p></td>
    <td><p>Amérique du Nord</p></td>
    <td><p>5 000</p></td>
    <td><p>2 000</p></td>
    <td><p>175</p></td>
    <td><p>1 400</p></td>
    <td><p>700</p></td>
    <td><p>172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</p></td>
    </tr>
    <tr class="even">
    <td><p>Reno</p></td>
    <td><p>Amérique du Nord</p></td>
    <td><p>10 000</p></td>
    <td><p>4 000</p></td>
    <td><p>175</p></td>
    <td><p>2 800</p></td>
    <td><p>700</p></td>
    <td><p>157.57.210.0/23, 172.28.151.128/25</p></td>
    </tr>
    <tr class="odd">
    <td><p>Portland</p></td>
    <td><p>Amérique du Nord</p></td>
    <td><p>5 000</p></td>
    <td><p>4 000</p></td>
    <td><p>175</p></td>
    <td><p>2 800</p></td>
    <td><p>700</p></td>
    <td><p>172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</p></td>
    </tr>
    <tr class="even">
    <td><p>New York</p></td>
    <td><p>Amérique du Nord</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</p></td>
    </tr>
    <tr class="odd">
    <td><p>Chicago</p></td>
    <td><p>Amérique du Nord</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>157.57.211.0/23, 172.28.152.128/25</p></td>
    </tr>
    <tr class="even">
    <td><p>Detroit</p></td>
    <td><p>Amérique du Nord</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>(aucune limite)</p></td>
    <td><p>172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</p></td>
    </tr>
    </tbody>
    </table>


7.  Dans le contrôle d’admission des appels de Lync Server, les connexions entre les régions réseau sont appelées *liaisons de région*. Pour chaque lien de région, déterminez ce qui suit, tout comme vous l’avez fait pour les sites réseau :
    
      - Limite de bande passante globale à appliquer à toutes les sessions audio simultanées. Si une nouvelle session audio entraîne la dépassement de cette limite, Lync Server ne permet pas à la session de démarrer.
    
      - Limite de bande passante à appliquer à chaque session audio individuelle. La bande passante CAC par défaut est de 175 Kbits/s, mais elle est modifiable par l’administrateur.
    
      - Limite de bande passante globale à appliquer à toutes les sessions vidéo simultanées. Si une nouvelle session vidéo ne peut pas être dépassée, Lync Server n’autorise pas le démarrage de la session.
    
      - Limite de bande passante à appliquer à chaque session vidéo individuelle. La bande passante CAC par défaut est de 700 Kbits/s, mais elle est modifiable par l’administrateur.
    
    **Liens de région réseau et limites de bande passante associées**
    
    ![Exemple de limitations entre 3 régions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Exemple de limitations entre 3 régions")  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a>Information de bande passante du lien de région (bande passante en Kbits/s)
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Nom de la liaison réseau</th>
    <th>Première région</th>
    <th>Seconde région</th>
    <th>Limite BP</th>
    <th>Limite audio</th>
    <th>Limite de session audio</th>
    <th>Limite vidéo</th>
    <th>Limite de session vidéo</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>NA-EMEA-LINK</p></td>
    <td><p>Amérique du Nord</p></td>
    <td><p>EMEA</p></td>
    <td><p>50 000</p></td>
    <td><p>20 000</p></td>
    <td><p>175</p></td>
    <td><p>14 000</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA-APAC-LINK</p></td>
    <td><p>EMEA</p></td>
    <td><p>APAC</p></td>
    <td><p>25 000</p></td>
    <td><p>10 000</p></td>
    <td><p>175</p></td>
    <td><p>7 000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


8.  Définissez un itinéraire entre chaque paire de régions réseau.
    
    <div>
    

    > [!NOTE]
    > Deux liaisons sont nécessaires à l’itinéraire entre les régions Amérique du Nord et APAC, car aucun lien de région ne les relie directement.

    
    </div>
    
    ### <a name="region-routes"></a>Itinéraires de région
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Nom de l’itinéraire</th>
    <th>Première région</th>
    <th>Seconde région</th>
    <th>Liens de région</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>NA-EMEA-ROUTE</p></td>
    <td><p>Amérique du Nord</p></td>
    <td><p>EMEA</p></td>
    <td><p>NA-EMEA-LINK</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA-APAC-ROUTE</p></td>
    <td><p>EMEA</p></td>
    <td><p>APAC</p></td>
    <td><p>EMEA-APAC-LINK</p></td>
    </tr>
    <tr class="odd">
    <td><p>NA-APAC-ROUTE</p></td>
    <td><p>Amérique du Nord</p></td>
    <td><p>APAC</p></td>
    <td><p>NA-EMEA-LINK, EMEA-APAC-LINK</p></td>
    </tr>
    </tbody>
    </table>


9.  Pour chaque paire de sites réseau directement connectée à une seule liaison (appelée liaison *intersite*), déterminez ce qui suit :
    
      - Limite de bande passante globale à appliquer à toutes les sessions audio simultanées. Si une nouvelle session audio entraîne la dépassement de cette limite, Lync Server ne permet pas à la session de démarrer.
    
      - Limite de bande passante à appliquer à chaque session audio individuelle. La bande passante CAC par défaut est de 175 Kbits/s, mais elle est modifiable par l’administrateur.
    
      - Limite de bande passante globale à appliquer à toutes les sessions vidéo simultanées. Si une nouvelle session vidéo ne peut pas être dépassée, Lync Server n’autorise pas le démarrage de la session.
    
      - Limite de bande passante à appliquer à chaque session vidéo individuelle. La bande passante CAC par défaut est de 700 Kbits/s, mais elle est modifiable par l’administrateur.
    
    **Région réseau CAC Amérique du Nord avec les capacités et les limites de bande passante de la liaison intersite entre Reno et Albuquerque**
    
    ![Exemple de sites réseau limités par la bande passante de la connexion WAN](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Exemple de sites réseau limités par la bande passante de la connexion WAN")  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a>Information de bande passante d’une liaison intersite entre deux sites réseau (bande passante en Kbits/s)
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Nom de la liaison intersite</th>
    <th>Premier site</th>
    <th>Second site</th>
    <th>Limite BP</th>
    <th>Limite audio</th>
    <th>Limite de session audio</th>
    <th>Limite vidéo</th>
    <th>Limite de session vidéo</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Reno-Albu-Intersite-Link</p></td>
    <td><p>Reno</p></td>
    <td><p>Albuquerque</p></td>
    <td><p>20 000</p></td>
    <td><p>12 000</p></td>
    <td><p>175</p></td>
    <td><p>5 000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a>Étapes suivantes

Après avoir recueilli les informations requises, vous pouvez effectuer un déploiement CAC à l’aide de Lync Server Management Shell ou du panneau de configuration de Lync Server.

<div>


> [!NOTE]
> Même si vous pouvez effectuer la plupart des tâches de configuration réseau en utilisant le panneau de configuration de Lync Server, afin de créer des sous-réseaux et des liaisons intersites, vous devez utiliser Lync Server Management Shell. Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell pour l’applet de <STRONG>nouvelle-CsNetworkSubnet</STRONG> et l’applet de <STRONG>nouvelle cmdlet New-CsNetworkIntersitePolicy</STRONG> .



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

