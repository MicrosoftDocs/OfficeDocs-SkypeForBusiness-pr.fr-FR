---
title: Qualité de service dans les équipes Microsoft - équipes Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: Serdars
ms.date: 04/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Préparez le réseau de votre organisation à la qualité de service (QoS) dans Microsoft Teams.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 884055dce490b9db8fd31f6e52042a4315633e00
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="quality-of-service-qos-in-microsoft-teams"></a>Qualité de service (QoS) dans Microsoft Teams

Cet article vous aidera à préparer le réseau de votre organisation de qualité de Service (QoS) dans Teams de Microsoft.
QoS est un mécanisme qui que vous permet de classer par priorité de certains types de trafic réseau. Il est important de fournir une expérience utilisateur de qualité professionnelle de hiérarchiser le trafic pour les services de communication en temps réel tels que des équipes. QoS être vraiment efficaces, vous devez configurer une connexion compatible QoS à partir de fin à fin (PC, commutateurs réseau et les routeurs vers le nuage), parce que n’importe quelle partie du chemin qui ne parvient pas à prendre en charge de QoS peut diminuer la qualité de l’appel de tout.

![La relation entre les réseaux d’une entreprise et les services Office 365 : réseau et périphériques de se connectent à un réseau d’interconnexion, qui à son tour se connecte aux services Office 365 nuage Audio la conférence vocale et sur site.] (media/Qos-in-Teams-Image1.png "La relation entre les réseaux d’une entreprise et les services Office 365 : réseau et périphériques de se connectent à un réseau d’interconnexion, qui à son tour se connecte aux services Office 365 nuage Audio la conférence vocale et sur site.")

_La figure 1. La relation entre les réseaux d’une entreprise et les services Office 365_
 

Dans la plupart des cas, le réseau d’interconnexion sera une connexion internet de réseau non géré. Une option permet de résoudre de QoS de bout en bout est [ExpressRoute d’Azure](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Nous vous recommandons quand même d’implémenter QoS sur des parties du réseau, vous pouvez contrôler, à savoir votre réseau local. Cela augmente la qualité des charges de travail de communication en temps réel tout au long de votre déploiement et réduire les goulots d’étranglement dans votre déploiement existant. 


## <a name="prioritize-teams-network-traffic-for-qos"></a>Hiérarchiser le trafic aux équipes de QoS 

Cet article se concentre sur la façon de hiérarchiser le trafic de communications en temps réel aux équipes — à savoir, la voix et la vidéo. Vous pouvez également classer les autres types de trafic, en fonction de vos besoins.

Il existe plusieurs façons de classer le trafic par ordre de priorité, mais la plus courante consiste à utiliser des marquages DSCP (Differentiated Services Code Point). Ils peuvent être appliqués (« balisage ») basés sur les plages de ports et également via des objets de stratégie de groupe. Nous traiterons dans cet article. Nous vous conseillons d’utiliser le balisage basé sur les plages de port car il fonctionnera pour tous les périphériques, et pas seulement ceux joints au domaine.

Contrôler le marquage DSCP via des objets de stratégie de groupe garantit que les ordinateurs joints au domaine reçoivent les paramètres corrects et que seul un administrateur peut gérer.
 
Il est important de comprendre que QoS ne fonctionne que lorsqu’elle est implémentée sur tous les liens qui se connectent de l’appelant à l’appelé. Si vous utilisez QoS sur le réseau interne et un utilisateur se connecte à partir d’un emplacement distant, vous pouvez classer uniquement au sein de votre réseau interne managé. Bien que les sites distants peuvent recevoir une connexion managée en implémentant un réseau privé virtuel (VPN), nous vous recommandons d’éviter d’exécuter le trafic des communications en temps réel via la connexion VPN.

> [!NOTE]
> Nous vous recommandons d’implémenter le tunneling fractionné connectés au VPN à distance aux utilisateurs d’optimiser la qualité de l’expérience utilisateur. Télécharger le document [Deploy-Guide-VPN fractionnement Tunnel](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ) à partir de MyAdvisor pour plus d’informations.

Dans une organisation internationale, avec des liens gérés qui s’étendent sur les continents, QoS est recommandé parce que la bande passante de ces liens est limitée en comparaison avec le réseau local.

## <a name="qos-queues"></a>Files d’attente de QoS

Pour fournir un niveau de service pour une application garanti sur le réseau, les périphériques réseau sous-jacent doivent avoir un moyen de classer les différents types de trafic. Si votre organisation souhaite donner la priorité du trafic voix sur d’autres types de trafic, un routeur (par exemple) doit être en mesure de faire la distinction entre le trafic vocal et le trafic normal de navigation sur le web. 

Services différenciés (DiffServ) fournit un cadre dans lequel le trafic a la priorité différents par les périphériques réseau en fonction du type de champ de services (ToS) dans l’en-tête d’un paquet IPv4/IPv6. Les six bits les plus significatifs du champ DiffServ sont le point de code de services différenciés ou DSCP. À l’aide de cette infrastructure, le trafic pouvant être considéré comme un type particulier de trafic (par exemple, voix) et puis marqué (46 en décimal pour le trafic vocal ou 101110), afin que les périphériques réseau traitent ces marques, le trafic peut être hiérarchisés en conséquence () Expedited Forwarding, dans cet exemple).

Le trafic réseau quand un routeur, le trafic est placé dans une file d’attente — si aucun QoS n’est en place, est essentiellement une file d’attente qu’une seule, et les données sont traitées comme, first-in, premier sorti. Cela signifie que le trafic vocal (ce qui est très sensible aux retards) peut être bloqué derrière le trafic à partir des services de diffusion de données en ligne. Lors de l’implémentation de qualité de service, vous pouvez définir plusieurs files d’attente à l’aide des fonctionnalités de gestion de congestion de différentes (telles que Cisco file d’attente prioritaire et classe pondérée juste file d’attente [CBWFQ]) et les fonctionnalités d’évitement de congestion (par exemple, pondérée aléatoire [de détection précoce WRED]).

![Bande passante totale disponible est répartie entre plusieurs files d’attente, audio, vidéo et autres types de trafic, qui vous ont été attribués des priorités différentes.] (media/Qos-in-Teams-Image2.png "Bande passante totale disponible est répartie entre plusieurs files d’attente, audio, vidéo et autres types de trafic, qui vous ont été attribués des priorités différentes.")

_La figure 2. Files d’attente de QoS de visualisation_

Une fois ces éléments en place, il est possible de livrer de qualité de service prévisible car le réseau managé sous-jacent comprend maintenant comment classer, de marquer et de hiérarchiser le trafic. Du point de vue des équipes, l’étape la plus importante de la configuration est la classification et le marquage des paquets, mais de QoS de bout en bout pour réussir, vous devez également Alignez soigneusement la configuration de l’application avec la configuration de réseau sous-jacent.

## <a name="teams-qos-scenarios"></a>Scénarios de QoS d’équipes

Le Guide pour l’implémentation de QoS pour les équipes est basé sur quatre scénarios :

*  **Le scénario 1 :** Vous avez déployé, ou que vous déployez, équipes et envisagez l’implémentation de QoS via le balisage basé sur le port. Basé sur le port de l’étiquetage est la méthode la plus fiable, car elle fonctionne de manière universelle sur l’ensemble de toutes les plates-formes et est très facile à implémenter.  

*  **Le scénario 2 :** Vous avez déployé, ou que vous déployez, équipes et envisagez de mettre en œuvre QoS via le marquage de l’objet stratégie de groupe. Cette méthode est parfois utilisée en conjonction avec le scénario 1. Bien que ce scénario soit entièrement valide, il est important de comprendre qu’il ne fonctionne que pour les clients Windows à un domaine. Tout périphérique qui n’est pas d’un client Windows à un domaine est désactivé pour le DSCP de repérage.

*  **Le scénario 3 :** Vous avez déployé le Skype pour professionnels en ligne, y compris QS et sont maintenant déployer des équipes. Si tel est le cas, Teams respectera la configuration existante et utilisera les même plages de ports et marquage que le client Skype Entreprise. Dans la plupart des cas, aucune configuration supplémentaire n’est nécessaire. 
 
    > [!NOTE]
    > Si vous utilisez des applications QoS de nom balisage via la stratégie de groupe, vous devez ajouter Teams.exe comme nom d’application.

*  **Scénario 4 :** Vous avez déployé, ou que vous déployez, équipes et à mettre en œuvre QoS via basée sur port le balisage à l’aide d’une plage de port personnalisé.

## <a name="recommended-dscp-markings"></a>Marquages de DSCP recommandés

La première étape consiste à classer les flux de trafic (par exemple, des données audio et vidéo) en assignant des valeurs DSCP pour les plages de ports uniques, sans chevauchement. La valeur DSCP affectée ici déterminera la priorité du trafic qui traverse le réseau, en fonction de la configuration du réseau. Chaque charge de travail obtient sa propre valeur DSCP, mais pas nécessairement une valeur unique, certains clients peuvent définir la même valeur pour les charges de travail voix et vidéo, en leur donnant le même niveau de priorité dans le réseau.  

La valeur DSCP à utiliser dépend de la façon dont vous souhaitez définir des priorités la charge de travail. Par exemple, les besoins de l’entreprise peuvent nécessiter que vous donnez à l’application partage la même priorité que la vidéo (et par conséquent le marquer avec la même valeur DSCP que la vidéo). Autres environnements peuvent avoir une stratégie de QoS existante en place, ce qui vous aidera à déterminer la priorité des charges de travail de réseau. 

Le tableau 1 présente les marquages de DSCP requis lors de l’utilisation d’équipes avec ExpressRoute. Ces marques peuvent être un bon point de départ pour les clients qui ne savez pas ce qu’il faut utiliser dans leurs propres environnements. Pour des informations complémentaire, consultez les [Exigences de qualité de service d’ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos).


_Le tableau 1. Marquages DSCP_
    
| Plage de port source client |Protocole|Catégorie de médias|Valeur DSCP|Classe DSCP|
|---------|---------|---------|---------|---------|
| 50 000 – 50,019|TCP/UDP|Audio|46|Acheminement accéléré (EF)|
| 50,020 – 50,039|TCP/UDP|Vidéo|34|Acheminement assuré (AF41)|
| 50,040 – 50,059|TCP/UDP|Partage d’application/de bureau|18|Assured Forwarding (AF21)|

Voici quelques précisions à comprendre lorsque vous utilisez les informations du tableau 1 :
    
-  Si vous envisagez d’implémenter ExpressRoute dans le futur et n’ont pas encore implémenté la qualité de service, nous vous recommandons de suivre les recommandations du tableau 1 afin que les valeurs DSCP sont identiques de l’expéditeur au destinataire. 

-  Tous les clients, y compris les clients mobiles et les périphériques des équipes, utiliseront ces plages de ports et seront affectés par une stratégie DSCP que vous implémentez qui utilise ces plages de port source. Les seuls clients qui vont continuer à utiliser des ports dynamiques sont les clients basés sur navigateur (autrement dit, les clients qui permettent aux participants de participer à des conférences à l’aide de leurs navigateurs).

-  Bien que le client Mac n’utilise pas les mêmes plages de ports, le client Mac utilise également des valeurs codées en dur audio (EF) et vidéo (AF41). Ces valeurs ne sont pas configurables.
 
    
## <a name="source-ports-used-by-teams"></a>Ports sources utilisés par Teams

Dans Teams, la qualité de service doit être configurée selon les ports sources utilisés par les différentes charges de travail. Aucun des deux plages de port côté serveur et côté client sont actuellement configurables. 

Notez les plages de port source client répertoriées dans le tableau 2 et d’utiliser leurs marques de QoS DSCP associées.

_Le tableau 2. Plages de port source client_

| Plage de port source client |Protocole|Catégorie de médias|Valeur DSCP|Classe DSCP|
|---------|---------|---------|---------|---------|
| 50 000 – 50,019|TCP/UDP|Audio|46|Acheminement accéléré (EF)|
| 50,020 – 50,039|TCP/UDP|Vidéo|34|Acheminement assuré (AF41)|
| 50,040 – 50,059|TCP/UDP|Partage d’application/de bureau|18|Assured Forwarding (AF21)|

La méthode recommandée d’implémentation de ces stratégies de qualité de service est d’utiliser les ports source client avec une adresse IP source et de destination de « tout ». Cela interceptera le trafic entrant et sortant de média sur le réseau interne. 

> [!NOTE]
> Si vous avez déjà configuré le QoS basé sur les plages de port source pour Skype for Business en ligne, la même configuration s’appliquera aux équipes et aucune modification supplémentaire n’est requise. Si vous avez déployé Skype pour Business Server locale, vous devrez recréer vos stratégies QoS.

## <a name="setting-dscp-markings"></a>Définition des marquages DSCP

Il existe plusieurs approches pour définir les marquages de DSCP appropriés pour la classification du trafic :

-  **Marquage DSCP au point de terminaison :** C’est généralement l’option préférée, car le point de terminaison fournit les indications appropriées. Actuellement le faire à l’aide d’un objet de stratégie de groupe, mais il peut être uniquement utilisé sur les clients Windows à un domaine. Les clients mobiles ne fournissent un mécanisme pour marquer le trafic à l’aide de valeurs DSCP. Bien que vous ne pouvez pas configurer non&ndash;à un domaine aux clients Windows de trafic de balise, les clients Mac OS ont des balises de codé en dur et permet toujours d’identifier le trafic comme décrit ci-dessus.

-  **Le balisage à l’aide de listes de contrôle d’accès (ACL) sur les routeurs DSCP basée sur le port :** Il s’agit d’une option très courante dans les environnements hétérogènes Windows et Mac. Dans ce scénario, l’équipe réseau marque le trafic sur les routeurs d’entrée/sortie (généralement situé sur le réseau WAN) basé sur les plages du port source définis pour chaque modalité. Bien que cela fonctionne sur plusieurs plates-formes, il identifie uniquement le trafic à la périphérie du réseau étendu, pas tout à fait à l’ordinateur client et entraîne par conséquent les frais de gestion.
    
-  **Une combinaison de marquages DSCP au point de terminaison et par port des ACL sur les routeurs :** Nous vous recommandons de cette combinaison, si possible dans votre environnement. Un objet de stratégie de groupe permet d’intercepter la plupart des clients et également utiliser DSCP basée sur port de repérage pour vous assurer que mobile, Mac et les autres clients reçoivent toujours traitement de QoS (au moins partiellement).
    
Vous pouvez utiliser basée sur une stratégie de QoS dans la stratégie de groupe pour définir la valeur DSCP pour la plage de ports source prédéfinis dans le client d’équipes. Les plages de port spécifiés dans le tableau 3 permet de créer une stratégie pour chaque charge de travail.

_Le tableau 3. Plages de ports par le type de trafic_
| Type de trafic du client|Début de la plage de ports|Fin de la plage de ports|Valeur DSCP|
|---------|---------|---------|--------|
| Audio|50000|50019|46|
| Vidéo|50020|50039|34|
| Partage d'application|50040|50059|18|

> [!NOTE]
> Les plages de ports définies par les équipes ne peut pas être modifiés. Consultez [cet article de la prise en charge](https://support.microsoft.com/kb/2409256) pour les informations les plus récentes. 

Après avoir identifié les plages de ports, l’étape suivante consiste à configurer les paramètres de QoS basée sur la stratégie dans un objet de stratégie de groupe. Vous trouverez plus d’informations sur ces étapes dans [cet article TechNet](https://technet.microsoft.com/library/jj205371(v=ocs.15).aspx). 

Les nouvelles stratégies que vous avez créé ne prennent effet tant que la stratégie de groupe a été actualisé sur vos ordinateurs clients. Bien que la stratégie de groupe actualise régulièrement sur son propre, vous pouvez forcer une actualisation immédiate.

### <a name="force-group-policy-refresh"></a>Actualisation de la stratégie de groupe

1. Sur chaque ordinateur pour lequel vous souhaitez actualiser la stratégie de groupe, ouvrez une console de commande. Assurez-vous que la console de commande est définie pour s’exécuter en tant qu’administrateur.

2. À l’invite de commandes, entrez :
```
    gpudate.exe /force
```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Vérifiez les marquages de DSCP dans l’objet stratégie de groupe

Pour vérifier que les valeurs de l’objet de stratégie de groupe ont été définies, effectuez les opérations suivantes.

1.  Ouvrez une console de commande. Assurez-vous que la console de commande est définie pour s’exécuter en tant qu’administrateur.

2.  À l’invite de commandes, entrez : 
    ```
    gpresult /R >gp.txt
    ```

    Cela va générer un rapport et l’envoyer à un fichier texte nommé gp.txt. Vous pouvez également entrer la commande suivante pour produire les mêmes données dans un rapport plus lisible en HTML nommé gp.html :
    ```
    gpresult /H >gp.html
    ```
 
   ![Capture d’écran de la fenêtre de console en cours d’exécution la commande gpresult.] (media/Qos-in-Teams-Image3.png "Capture d’écran de la fenêtre de console en cours d’exécution la commande gpresult.")

3.  Dans le fichier généré, recherchez la rubrique **Objets de stratégie de groupe appliqués** et vérifiez que les noms des objets de stratégie de groupe créés précédemment sont dans la liste des stratégies appliquées. 

4.  Ouvrez l’Éditeur du Registre et accédez à :

    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

    Vérifiez les valeurs pour les entrées de Registre répertoriées dans le tableau 3.

    _Le tableau 3. Valeurs des entrées du Registre Windows pour QoS_
    
    | Nom | Type | Données|
    |---------|---------|---------
    | Nom de l’application|REG_SZ|Teams.exe|
    | Valeur DSCP|REG_SZ|46|
    | Adresse IP locale|REG_SZ|*|
    | Longueur du préfixe de l’adresse IP locale|REG_SZ|*|
    | Port local|REG_SZ|50000-50019|
    | Protocole|REG_SZ|*|
    | Adresse IP distante|REG_SZ|*|
    | Préfixe de l’adresse IP distante|REG_SZ|*|
    | Port distant|REG_SZ|*|
    | Taux d’accélération|REG_SZ|-1|
    
5.  Vérifiez que la valeur de l’entrée du nom de l’Application est correcte pour le client que vous utilisez et vérifiez que les entrées de la valeur DSCP et le Port Local reflètent les paramètres dans l’objet stratégie de groupe.

## <a name="validate-qos-by-analyzing-teams-traffic-on-the-network"></a>Valider la QoS en analysant le trafic des équipes sur le réseau

La valeur DSCP est définie par l’objet stratégie de groupe doit être présent à partir de l’appelant à l’appelé dans l’ordre de qualité de service être efficace. En observant le trafic généré par le client d’équipes, vous pouvez vérifier que la valeur DSCP n’est pas modifiée ou supprimée lorsque le trafic de la charge de travail des équipes voyagent sur le réseau. 

De préférence, vous capturez le trafic au niveau du point de sortie du réseau. Vous pouvez utiliser la mise en miroir de port sur un commutateur ou un routeur pour cela.

### <a name="use-network-monitor-to-verify-dscp-values"></a>Utilisez le Moniteur réseau pour vérifier les valeurs DSCP

Le Moniteur réseau est un outil que vous pouvez [télécharger à partir de Microsoft](https://www.microsoft.com/download/4865) pour analyser le trafic réseau.

1.  Sur l’ordinateur exécutant le Moniteur réseau, se connecter au port qui a été configuré pour la mise en miroir des ports et démarrer la capture des paquets. 

2.  Effectuer un appel à l’aide de la Skype pour client d’entreprise. Assurez-vous que le support a été établie avant de raccrocher à l’appel. 

3.  Arrêter la capture.

4. Dans le champ **Filtre d’affichage** , utilisez l’adresse IP source de l’ordinateur qui a effectué l’appel et affiner le filtre en définissant la valeur DSCP 46 (hex d’arrêt 0xb8) comme critère de recherche, comme illustré dans l’exemple suivant :

    Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8 

    ![Capture d’écran de la boîte de dialogue filtre d’affichage dans le Moniteur réseau, montrant des filtres à appliquer.] (media/Qos-in-Teams-Image4.png "Capture d’écran de la boîte de dialogue filtre d’affichage dans le Moniteur réseau, montrant des filtres à appliquer.")

5.  Sélectionnez **Appliquer** pour activer le filtre.

6.  Dans la fenêtre **Résumé de l’image** , sélectionnez le premier paquet UDP.

7.  Dans la fenêtre **Détails de la trame** , développez l’élément de liste IPv4 et notez la valeur à la fin de la ligne qui commence par le **DSCP**. 

    ![Capture d’écran de la boîte de dialogue Détails de l’image dans le Moniteur réseau, mise en surbrillance de paramètres de DSCP.] (media/Qos-in-Teams-Image5.png "Capture d’écran de la boîte de dialogue Détails de l’image dans le Moniteur réseau, mise en surbrillance de paramètres de DSCP.")

Dans cet exemple, la valeur DSCP est définie à 46. Cela est correct, car le port source utilisé est 50019, qui indique qu’il s’agit d’une charge de travail des voix. 

Répétez cette vérification pour chaque charge de travail qui a été marquée par l’objet de stratégie de groupe. 
