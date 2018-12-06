---
title: "Lync Server 2013 : ex. coll. données de la conf. req. pr contr. adm. appels"
TOCTitle: 'Exemple : collecte des données de la configuration requise de votre organisation pour le contrôle d’admission des appels dans Lync Server 2013'
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425827(v=OCS.15)
ms:contentKeyID: 49296810
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exemple : collecte des données de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Cet exemple indique comment planifier et implémenter le contrôle d’admission des appels (CAC). Globalement, il s’agit des activités suivantes :

1.  Identifiez l’ensemble de vos concentrateurs réseau et dorsales principales (connues aussi sous le nom de *régions réseau* ).

2.  Identifiez le site central Lync Server chargé de gérer le contrôle d’admission des appels sur chaque région réseau.

3.  Identifiez et définissez les *sites réseau* connectés à chaque région réseau.

4.  Pour chaque site réseau dont la bande passante de connexion du réseau étendu est limitée, décrivez la bande passante et les limites de bande passante que l’administrateur du réseau a configurées pour le trafic multimédia de Lync Server, le cas échéant. Il n’est pas nécessaire d’inclure les sites dont la bande passante de connexion de réseau étendu n’est pas limitée.

5.  Associez chaque sous-réseau de votre réseau à un site réseau.

6.  Mappez les liaisons entre régions réseau. Pour chaque liaison, décrivez sa capacité de bande passante et toute limite imposée par l’administrateur système sur le trafic multimédia de Lync Server.

7.  Définissez un itinéraire entre chaque paire de régions réseau.

## Rassembler les informations requises

Pour préparer le contrôle d’admission des appels, rassemblez les informations présentées dans les étapes suivantes :

1.  Identifiez vos régions réseau. Une région réseau représente une dorsale principale ou un concentrateur réseau.
    
    Une dorsale principale ou un concentrateur réseau fait partie de l’infrastructure réseau informatique qui interconnecte différents éléments du réseau, fournissant ainsi un chemin pour l’échange des informations entre différents réseaux locaux (LAN) ou sous-réseaux. Une dorsale principale peut lier divers réseaux d’un petit emplacement à une zone géographique étendue. La capacité de la dorsale principale est généralement plus grande que celle des réseaux qui s’y connectent.
    
    Notre exemple de topologie comporte trois régions réseau : Amérique du Nord, EMEA et APAC. Une région réseau contient une collection de sites réseau. Définissez les régions réseau de votre entreprise avec l’administrateur réseau.

2.  Identifiez le site central associé à chaque région réseau. Un site central contient au moins un serveur frontal et constitue le déploiement Lync Server qui sera chargé de gérer la fonctionnalité CAC pour tout le trafic multimédia transitant via la connexion de réseau étendu de la région réseau.
    
    **Exemple de réseau d’entreprise divisé en trois régions réseau**
    
    ![Exemple de topologie réseau avec 3 régions réseau](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Exemple de topologie réseau avec 3 régions réseau")  
    
    > [!NOTE]  
    > Un réseau MPLS (Multiprotocol Label Switching) devrait être représenté en tant que région réseau dans laquelle un emplacement géographique est associé à un site réseau correspondant. Pour plus d’informations, reportez-vous à la rubrique «  <a href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Contrôle d’admission des appels sur un réseau MPLS avec Lync Server 2013</a> » dans la documentation de planification.    
    
    
    L’exemple de topologie réseau précédent présente trois régions réseau, chacune comportant un site central Lync Server qui gère la fonctionnalité CAC. Le site central convenant le mieux à une région réseau est déterminé en fonction de la proximité géographique. Comme le trafic multimédia est susceptible d’être le plus important au sein d’une même région réseau, le fait d’opter pour la proximité géographique rend la fonctionnalité CAC indépendante. Celle-ci continuera de fonctionner même en cas d’indisponibilité d’autres sites centraux.
    
    Dans cet exemple, un déploiement Lync Server nommé Chicago est le site central de la région Amérique du Nord.
    
    Tous les utilisateurs Lync basés en Amérique du Nord sont hébergés sur des serveurs du déploiement Chicago. Le tableau ci-dessous répertorie les sites centraux pour les trois régions réseau.
    
    ### Régions réseau et leur site central associé
    
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
    
    > [!NOTE]  
    > Selon votre topologie Lync Server, vous pouvez affecter le même site central à plusieurs régions réseau.

3.  Pour chaque région réseau, identifiez tous les sites réseau (bureaux ou emplacements) dont les connexions au réseau étendu ne sont pas soumises à une limite de bande passante. Comme ces sites disposent de liaisons réseau dont la bande passante n’est pas limitée, il n’est pas nécessaire de leur appliquer des stratégies de bande passante CAC.
    
    Dans l’exemple présenté dans le tableau suivant, trois sites réseau disposent de liaisons réseau dont la bande passante n’est pas limitée : New York, Chicago et Détroit.
    
    ### Sites réseau non limités par la bande passante de la connexion de réseau étendu
    
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
    
    Pour garantir la qualité de l’audio et de la vidéo, nous recommandons de surveiller les réseaux de réseau étendu des sites dont la bande passante est limitée et d’imposer des stratégies de bande passante CAC limitant le flux multimédia (vocal ou vidéo) depuis et vers la région réseau.
    
    Dans l’exemple présenté dans le tableau suivant, trois sites réseaux sont limités par la bande passante du réseau étendu : Portland, Reno et Albuquerque.
    
    ### Sites réseau limités par la bande passante de la connexion de réseau étendu
    
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
    
      - Limite de bande passante globale à appliquer à toutes les sessions audio simultanées. Si une nouvelle session audio entraîne le dépassement de la limite, Lync Server empêche le démarrage de la session.
    
      - Limite de bande passante à appliquer à chaque session audio individuelle. La bande passante CAC par défaut est de 175 Kbits/s, mais elle est modifiable par l’administrateur.
    
      - Limite de bande passante globale à appliquer à toutes les sessions vidéo simultanées. Si une nouvelle session vidéo entraîne le dépassement de la limite, Lync Server empêche le démarrage de la session.
    
      - Limite de bande passante à appliquer à chaque session vidéo individuelle. La bande passante CAC par défaut est de 700 Kbits/s, mais elle est modifiable par l’administrateur.
    
    ### Sites réseau et informations de restriction de bande passante de réseau étendu (bande passante en Kbits/s)
    
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
    
    > [!IMPORTANT]  
    > Chaque sous-réseau doit être associé à un site réseau, même si le site réseau n’est pas soumis à une limite de bande passante. Cela est dû au fait que le contrôle d’admission des appels utilise les informations relatives aux sous-réseaux pour déterminer sur quel site réseau un point de terminaison doit se situer. Lorsque les emplacements de chaque partie de la session sont déterminés, le contrôle d’admission des appels peut déterminer si la bande passante est suffisante pour établir l’appel. Lorsqu’une session est établie sur une liaison dont la bande passante n’est pas limitée, une alerte est générée.<br />
    Si vous déployez des serveurs Edge A/V, les adresses IP publiques de chaque serveur Edge doivent être associées au site réseau sur lequel le serveur Edge est déployé. Vous devez ajouter chaque adresse IP publique du serveur Edge A/V à vos paramètres de configuration réseau en tant que sous-réseau avec un masque de sous réseau de 32. Par exemple, si vous déployez des serveurs Edge A/V à Chicago, pour chaque adresse IP externe de ces serveurs, créez un sous-réseau avec un masque de sous-réseau de 32 et associez le site réseau Chicago à ces sous-réseaux. Pour plus d’informations sur les adresses IP publiques, reportez-vous à <a href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013</a> dans la documentation de planification.  

    > [!NOTE]  
    > Une alerte d’indicateur d’intégrité clé est générée, indiquant une liste d’adresses IP figurant dans votre réseau, mais non associées à un sous-réseau ou figurant dans un sous-réseau non associé à un site réseau. L’alerte n’est générée qu’une seule fois par période de 8 heures. Les informations d’alerte pertinentes et un exemple sont présentés ci-dessous :<br />
    <strong>Source</strong> : Service de stratégie de bande passante (principal) CS<br />
    <strong>Numéro d’événement</strong> : 36034<br />
    <strong>Niveau</strong> : 2<br />
    <strong>Description</strong> : les sous-réseaux pour les adresses IP suivantes ne sont pas configurés ou les sous-réseaux ne sont pas associés à un site réseau : &lt;liste d’adresses IP&gt;.<br />
    <strong>Cause</strong> : les sous-réseaux pour les adresses IP correspondantes sont absents des paramètres de configuration du réseau ou les sous-réseaux ne sont pas associés à un site réseau.<br />
    <strong>Résolution</strong> : ajoutez les sous-réseaux pour les adresses IP correspondantes aux paramètres de configuration du réseau et associez chaque sous-réseau à un site réseau.<br />
    Par exemple, si la liste d’adresses IP qui s’affiche dans l’alerte indique 10.121.248.226 et 10.121.249.20, soit ces adresses IP ne sont pas associées à un sous-réseau, soit le sous-réseau auquel elles sont associées n’appartient pas au site réseau. Si 10.121.248.0/24 et 10.121.249.0/24 sont les sous-réseaux associés à ces adresses, vous pouvez résoudre le problème comme suit :<ol><li><p>Vérifiez que l’adresse IP 10.121.248.226 est associée au sous-réseau 10.121.248.0/24 et l’adresse IP 10.121.249.20 au sous-réseau 10.121.249.0/24.</p></li><li><p>Vérifiez que les sous-réseaux 10.121.248.0/24 et 10.121.249.0/24 sont chacun associés à un site réseau.</p></li>    </ol>
    
### Sites réseau et sous-réseaux associés (bande passante en Kbits/s)
    
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


7.  Dans le contrôle d’admission des appels Lync Server, les connexions entre régions réseau sont appelées *liens de région* . Pour chaque lien de région, déterminez ce qui suit, tout comme vous l’avez fait pour les sites réseau :
    
      - Limite de bande passante globale à appliquer à toutes les sessions audio simultanées. Si une nouvelle session audio entraîne le dépassement de la limite, Lync Server empêche le démarrage de la session.
    
      - Limite de bande passante à appliquer à chaque session audio individuelle. La bande passante CAC par défaut est de 175 Kbits/s, mais elle est modifiable par l’administrateur.
    
      - Limite de bande passante globale à appliquer à toutes les sessions vidéo simultanées. Si une nouvelle session vidéo entraîne le dépassement de la limite, Lync Server empêche le démarrage de la session.
    
      - Limite de bande passante à appliquer à chaque session vidéo individuelle. La bande passante CAC par défaut est de 700 Kbits/s, mais elle est modifiable par l’administrateur.
    
    **Liens de région réseau et limites de bande passante associées**
    
    ![Exemple de limitations entre 3 régions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Exemple de limitations entre 3 régions")  
    
    ### Information de bande passante du lien de région (bande passante en Kbits/s)
    
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
    
    > [!NOTE]  
    > Deux liaisons sont nécessaires à l’itinéraire entre les régions Amérique du Nord et APAC, car aucun lien de région ne les relie directement.    
    ### Itinéraires de région
    
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


9.  Pour chaque paire de sites réseau directement connectée à une seule liaison (appelée liaison *intersite* ), déterminez ce qui suit :
    
      - Limite de bande passante globale à appliquer à toutes les sessions audio simultanées. Si une nouvelle session audio entraîne le dépassement de la limite, Lync Server empêche le démarrage de la session.
    
      - Limite de bande passante à appliquer à chaque session audio individuelle. La bande passante CAC par défaut est de 175 Kbits/s, mais elle est modifiable par l’administrateur.
    
      - Limite de bande passante globale à appliquer à toutes les sessions vidéo simultanées. Si une nouvelle session vidéo entraîne le dépassement de la limite, Lync Server empêche le démarrage de la session.
    
      - Limite de bande passante à appliquer à chaque session vidéo individuelle. La bande passante CAC par défaut est de 700 Kbits/s, mais elle est modifiable par l’administrateur.
    
    **Région réseau CAC Amérique du Nord avec les capacités et les limites de bande passante de la liaison intersite entre Reno et Albuquerque**
    
    ![Exemple de sites réseau limités par la bande passante de la connexion WAN](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Exemple de sites réseau limités par la bande passante de la connexion WAN")  
    
    ### Information de bande passante d’une liaison intersite entre deux sites réseau (bande passante en Kbits/s)
    
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


## Étapes suivantes

Une fois que vous avez rassemblé toutes les informations requises, vous pouvez procéder au déploiement de la fonctionnalité CAC à l’aide de Lync Server Management Shell ou du Panneau de configuration Lync Server.

> [!NOTE]  
> Même si vous pouvez exécuter la plupart des tâches de configuration du réseau à l’aide du Panneau de configuration Lync Server, vous devez utiliser Lync Server Management Shell pour créer les sous-réseaux et les liaisons intersites. Pour plus d’informations, reportez-vous aux ²applets de commande <strong>New-CsNetworkSubnet</strong> et <strong>New-CsNetworkIntersitePolicy</strong> dans la documentation Lync Server Management Shell.
