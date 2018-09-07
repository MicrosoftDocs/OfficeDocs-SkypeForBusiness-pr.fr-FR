---
title: Qualité de Service dans les équipes Microsoft - équipes Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: Serdars
ms.date: 04/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Préparez le réseau de votre organisation à la qualité de service (QoS) dans Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b469c54f12e84e5f342b10a186893f16e229d04
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861282"
---
# <a name="quality-of-service-qos-in-microsoft-teams"></a>Qualité de service (QoS) dans Microsoft Teams

Cet article vous aide à préparer le réseau de votre organisation de qualité de Service (QoS) dans Microsoft Teams.
QoS est un mécanisme qui que vous permet de définir la priorité certains types de trafic réseau. Définition des priorités du trafic des services de communication en temps réel tels que des équipes sont important de fournir une expérience utilisateur de qualité professionnelle. QoS être vraiment efficace, vous devez configurer une connexion prenant en charge la qualité de service à partir de fin à fin (PC, commutateurs réseau et routeurs vers le nuage), parce que n’importe quelle partie du chemin qui échoue pour prendre en charge QoS peut diminuer la qualité de l’appel entière.

![La relation entre les réseaux d’une organisation et les services Office 365 : réseau et périphériques de se connectent à un réseau d’interconnexion, qui se connecte à son tour avec les services Office 365 Cloud voix et de conférence sur site.] (media/Qos-in-Teams-Image1.png "La relation entre les réseaux d’une organisation et les services Office 365 : réseau et périphériques de se connectent à un réseau d’interconnexion, qui se connecte à son tour avec les services Office 365 Cloud voix et de conférence sur site.")

_La figure 1. La relation entre les réseaux d’une organisation et les services Office 365_
 

Dans la plupart des cas, le réseau d’interconnexion sera une connexion internet de réseau non géré. Une seule option disponible pour résoudre QoS de bout en bout est [ExpressRoute Azure](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Nous vous recommandons d’implémenter QoS sur les parties du réseau, vous pouvez contrôler, à savoir votre réseau local. Cette augmentation de la qualité des charges de travail de communication en temps réel au sein de votre déploiement et éviter les goulots d’étranglement dans votre déploiement existant. 


## <a name="prioritize-teams-network-traffic-for-qos"></a>Hiérarchiser les équipes le trafic pour QoS 

Cet article explique comment définir la priorité le trafic des communications en temps réel les équipes, à savoir, audio et vidéo. Vous pouvez également classer les autres types de trafic, en fonction de vos besoins.

Il existe plusieurs façons de classer le trafic par ordre de priorité, mais la plus courante consiste à utiliser des marquages DSCP (Differentiated Services Code Point). Elles peuvent être appliquées (« balisage ») en fonction des plages de ports et également via des objets de stratégie de groupe. Sujets abordés dans cet article. Nous vous recommandons d’utiliser le balisage basé sur les plages de ports, car elle fonctionne pour tous les périphériques, pas seulement ceux liés au domaine.

Contrôler le marquage DSCP via des objets de stratégie de groupe garantit que les ordinateurs à un domaine recevant les paramètres corrects et que seul un administrateur peut gérer.
 
Il est important de comprendre la qualité de service fonctionne uniquement lorsqu’elle est implémentée sur tous les liens qui se connectent de l’appelant vers l’appelé. Si vous utilisez QoS sur le réseau interne et un utilisateur se connecte à partir d’un emplacement distant, vous pouvez classer uniquement au sein de votre réseau interne, gérée. Bien que les sites distants peuvent recevoir une connexion gérée en implémentant un réseau privé virtuel (VPN), nous vous recommandons d’éviter d’exécuter le trafic des communications en temps réel via la connexion VPN.

> [!NOTE]
> Il est recommandé d’implémenter le fractionnement tunnel pour les utilisateurs distants connectés VPN optimiser la qualité de l’expérience utilisateur. Télécharger le document [Guide de déploiement-VPN fractionné Tunnel](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ) à partir de MyAdvisor pour plus d’informations.

Dans une organisation globale avec liens gérées qui couvrent continents, QoS est vivement recommandé de bande passante pour ces liens étant limitée en comparaison avec le réseau local.

## <a name="qos-queues"></a>Files d’attente de QoS

Pour fournir un niveau de service pour une application garanti sur le réseau, les périphériques réseau sous-jacent doivent avoir un moyen de classer les différents types de trafic. Si votre organisation souhaite donne la priorité de trafic de voix trafic, un routeur (par exemple) doit être en mesure de faire la distinction entre le trafic vocal et le trafic de navigation web normal. 

Services différenciés (DiffServ) fournit une infrastructure dans laquelle le trafic a la priorité différents par les périphériques réseau en fonction du type de champ services (ToS) dans l’en-tête d’un paquet IPv4/IPv6. Les six bits les plus significatifs du champ DiffServ sont le point de code de services différenciés ou DSCP. À l’aide de cette infrastructure, le trafic pouvant être considéré comme un type particulier de trafic (par exemple, voix) et puis marqué (101110 ou 46 en décimal pour le trafic vocal), afin que les périphériques réseau traitent ces marquages, le trafic peut être hiérarchisée en conséquence () Expedited Forwarding, dans cet exemple).

Le trafic réseau quand un routeur, le trafic est placé dans une file d’attente : Si aucun QoS n’est en place, essentiellement n'est qu’une seule file d’attente et les données sont considérées comme première-in, sorti. Cela signifie que le trafic vocal (qui est très sensible aux délais) peut être bloqué derrière le trafic des services de diffusion en continu en ligne. Lors de l’implémentation de qualité de service, vous pouvez définir plusieurs files d’attente en utilisant les fonctionnalités de réductions congestion (par exemple, pondérée aléatoire [de détection au plus tôt et les fonctionnalités de gestion de congestion différents (tels que Cisco priorité et basé sur une classe weighted fair file d’attente [CBWFQ]) WRED]).

![La bande passante disponible total est répartie entre plusieurs files d’attente, audio, vidéo et autres types de trafic, qui ont été attribués à des priorités différentes.] (media/Qos-in-Teams-Image2.png "La bande passante disponible total est répartie entre plusieurs files d’attente, audio, vidéo et autres types de trafic, qui ont été attribués à des priorités différentes.")

_La figure 2. Files d’attente de QoS affichées_

Une fois ces éléments sont en place, il est possible de remettre QoS prévisible parce que le réseau géré sous-jacent comprend désormais comment classer, de marquer et de définir la priorité du trafic. Du point de vue des équipes, l’étape de configuration plus importante est la classification et le marquage des paquets, mais pour QoS de bout en bout aboutisse, vous devez également Alignez soigneusement la configuration de l’application avec la configuration réseau sous-jacente.

## <a name="teams-qos-scenarios"></a>Scénarios de QoS des équipes

Les instructions pour l’implémentation de QoS pour les équipes repose sur quatre scénarios :

*  **Scénario 1 :** Vous avez déployé, ou déployez, équipes et envisagez l’implémentation de QoS via le balisage basé sur un port. Balisage basé sur le port est la méthode la plus fiable, car elle fonctionne de manière universelle tout au long de toutes les plateformes et est très facile à implémenter.  

*  **Scénario 2 :** Vous avez déployé, ou déployez, équipes et envisagez d’implémenter QoS par le biais de la liaison d’objet de stratégie de groupe. Cette méthode est parfois utilisée en conjonction avec le scénario 1. Bien que ce scénario est entièrement valide, il est important de comprendre qu’il fonctionne uniquement pour les clients à un domaine Windows. Tous les périphériques qui n’est pas un client Windows à un domaine ne sont pas être activé pour le marquage DSCP marquage.

*  **Scénario 3 :** Vous avez déployé Skype pour Business en ligne, y compris QoS mise en réseau et déployez maintenant équipes. Si tel est le cas, Teams respectera la configuration existante et utilisera les même plages de ports et marquage que le client Skype Entreprise. Dans la plupart des cas, aucune configuration supplémentaire n’est nécessaire. 
 
    > [!NOTE]
    > Si vous utilisez des applications nom QoS balisage via la stratégie de groupe, vous devez ajouter Teams.exe comme nom d’application.

*  **Scénario 4 :** Vous avez déployé, ou que vous déployez, équipes et que vous souhaitez implémenter QoS via basée sur le port de liaison à l’aide d’une plage de ports personnalisés.

## <a name="recommended-dscp-markings"></a>Marquages DSCP recommandés

La première étape consiste à classer les flux de trafic (tels que les paramètres audio / vidéo) en assignant des valeurs DSCP pour les plages de ports unique, sans chevauchement. La valeur DSCP affectée ici détermine la priorité du trafic via le réseau, en fonction de la configuration réseau. Chaque charge de travail obtient sa propre valeur DSCP, mais pas nécessairement une valeur unique, certains clients peuvent définir la même valeur pour les charges de travail voix et vidéo, en leur donnant le même niveau de priorité dans le réseau.  

La valeur DSCP à utiliser dépend de la manière dont vous souhaitez définir la priorité la charge de travail. Par exemple, les impératifs peuvent nécessiter que vous donnez application partage la même priorité que la vidéo (et par conséquent marquez-le avec la même valeur DSCP en tant que vidéo). Autres environnements peuvent avoir une stratégie de QoS existante en place, qui vous aideront à déterminer la priorité des charges de réseau. 

Le tableau 1 présente le marquage DSCP requis lors de l’utilisation d’équipes avec ExpressRoute. Ces marquages peuvent être un bon point de départ pour les clients qui ne savez pas comment utiliser dans leurs propres environnements. Pour des informations complémentaire, consultez les [Exigences de qualité de service d’ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos).


_Le tableau 1. Marquage DSCP_
    
| Plage de ports client source |Protocole|Catégorie de médias|Valeur DSCP|Classe DSCP|
|---------|---------|---------|---------|---------|
| 50 000 – 50,019|TCP/UDP|Audio|46|Acheminement accéléré (EF)|
| 50,020 – 50,039|TCP/UDP|Vidéo|34|Acheminement assuré (AF41)|
| 50,040 – 50,059|TCP/UDP|Application/partage du bureau|18|Assured Forwarding (AF21)|

Voici quelques précisions à comprendre lorsque vous utilisez les informations du tableau 1 :
    
-  Si vous envisagez d’implémenter ExpressRoute dans le futur et n’ont pas encore implémenté QoS, nous vous recommandons que vous suivez les instructions dans le tableau 1 afin que les valeurs DSCP sont les mêmes à partir de l’expéditeur au récepteur. 

-  Tous les clients, y compris les clients mobiles et les périphériques d’équipes, utiliseront ces plages de ports et seront affectés par une stratégie DSCP que vous implémentez qui utilise ces plages de ports source. Seuls les clients qui continueront à utiliser des ports dynamiques sont les clients basés sur navigateur (autrement dit, les clients qui permettent aux participants de participer à des réunions à l’aide de leurs navigateurs).

-  Même si le client Mac n’utilise pas les mêmes plages de ports, le client Mac utilise également des valeurs codées en dur audio (EF) et vidéo (AF41). Ces valeurs ne sont pas configurables.
 
    
## <a name="source-ports-used-by-teams"></a>Ports sources utilisés par Teams

Dans Teams, la qualité de service doit être configurée selon les ports sources utilisés par les différentes charges de travail. Aucun des deux plages de ports côté serveur et côté client sont actuellement configurables. 

Notez les plages de ports source client répertoriées dans le tableau 2 et utiliser leur marquage QoS DSCP associée.

_Le tableau 2. Plages de ports client source_

| Plage de ports client source |Protocole|Catégorie de médias|Valeur DSCP|Classe DSCP|
|---------|---------|---------|---------|---------|
| 50 000 – 50,019|TCP/UDP|Audio|46|Acheminement accéléré (EF)|
| 50,020 – 50,039|TCP/UDP|Vidéo|34|Acheminement assuré (AF41)|
| 50,040 – 50,059|TCP/UDP|Application/partage du bureau|18|Assured Forwarding (AF21)|

La méthode d’implémentation de ces stratégies QoS recommandée consiste à utiliser les ports source client avec une adresse IP source et de destination de « indifférent ». Ceci permet de détecter les deux le trafic multimédia entrant et sortant sur le réseau interne. 

> [!NOTE]
> Si vous avez déjà configuré QoS basée sur les plages de ports source pour Skype for Business en ligne, la même configuration s’appliquera aux équipes et aucune modification supplémentaire ne sera requise. Si vous avez déployé Skype pour Business Server locale, vous devrez recréer vos stratégies QoS.

## <a name="setting-dscp-markings"></a>Définition de marquage DSCP

Il existe plusieurs approches pour définir les marques DSCP appropriées pour la classification de trafic :

-  **Le marquage DSCP au point de terminaison :** C’est généralement l’option recommandée, car le point de terminaison fournit les inscriptions appropriées. Actuellement cela à l’aide d’un objet de stratégie de groupe, mais il peut uniquement être utilisé sur les clients à un domaine Windows. Les clients mobiles ne fournissent un mécanisme pour marquer le trafic à l’aide de valeurs DSCP. Bien que vous ne pouvez pas configurer non&ndash;à un domaine clients au trafic balise, clients tels que Mac OS les balises codé en dur et Windows sera balise toujours le trafic comme indiqué ci-dessus.

-  **DSCP basée sur le port de liaison à l’aide de listes de contrôle d’accès (ACL) sur les routeurs :** Il s’agit d’une option très courante rencontrée dans les environnements hétérogènes Windows et Mac. Dans ce scénario, l’équipe réseau marque le trafic sur les routeurs d’entrée/sortie (généralement situé sur le réseau étendu) basé sur les plages de ports source définies pour chaque modalité. Bien que cela fonctionne sur plusieurs plates-formes, il marque uniquement le trafic sur le bord WAN — pas tout à fait à l’ordinateur client et par conséquent entraîne une surcharge de gestion.
    
-  **Une combinaison de marquage DSCP au point de terminaison et ACL basées sur des ports sur les routeurs :** Nous vous recommandons de cette combinaison, si possible dans votre environnement. Utilisez un objet de stratégie de groupe pour intercepter la plupart des clients et également utiliser DSCP basée sur le port de marquage pour vous assurer que mobile, Mac et les autres clients seront toujours traitement QoS (au moins partiellement).
    
Vous pouvez utiliser QoS basée sur les stratégies au sein de la stratégie de groupe pour définir la valeur DSCP pour la plage de ports source prédéfinis dans le client d’équipes. Pour créer une stratégie pour chaque charge de travail, utilisez les plages de ports spécifiés dans le tableau 3.

_Le tableau 3. Plages de ports par type de trafic_
| Type de trafic du client|Début de la plage de ports|Fin de la plage de ports|Valeur DSCP|
|---------|---------|---------|--------|
| Audio|50000|50019|46|
| Vidéo|50020|50039|34|
| Partage d'application|50040|50059|18|

> [!NOTE]
> Les plages de ports définies par les équipes ne peut pas être modifiés. Consultez [cet article du support technique](https://support.microsoft.com/kb/2409256) pour obtenir les dernières informations. 

Une fois que vous avez identifié les plages de ports, l’étape suivante consiste à configurer les paramètres QoS basée sur la stratégie dans un objet de stratégie de groupe. Vous trouverez plus d’informations sur ces étapes dans [cet article TechNet](https://technet.microsoft.com/library/jj205371(v=ocs.15).aspx). 

Les nouvelles stratégies que vous avez créé ne prennent effet tant que la stratégie de groupe a été actualisée sur vos ordinateurs clients. Bien que la stratégie de groupe est actualisée régulièrement sur son propre, vous pouvez forcer une actualisation immédiate.

### <a name="force-group-policy-refresh"></a>Actualisation de la stratégie de groupe

1. Sur chaque ordinateur pour lequel vous voulez actualiser la stratégie de groupe, ouvrez une console de commande. Assurez-vous que la console de commande est définie sur Exécuter en tant qu’administrateur.

2. À l’invite de commandes, entrez
```
    gpudate.exe /force
```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Vérifier le marquage DSCP dans l’objet de stratégie de groupe

Pour vérifier que les valeurs de l’objet de stratégie de groupe ont été définies, procédez comme suit.

1.  Ouvrez une console de commande. Assurez-vous que la console de commande est définie sur Exécuter en tant qu’administrateur.

2.  À l’invite de commandes, entrez 
    ```
    gpresult /R >gp.txt
    ```

    Cela générer un rapport et envoyez-le à un fichier texte nommé gp.txt. Vous pouvez également entrer la commande suivante pour produire les mêmes données dans un rapport HTML plus lisible nommé gp.html :
    ```
    gpresult /H >gp.html
    ```
 
   ![Capture d’écran de la fenêtre de console exécutant la commande gpresult.] (media/Qos-in-Teams-Image3.png "Capture d’écran de la fenêtre de console exécutant la commande gpresult.")

3.  Dans le fichier généré, recherchez l’en-tête **Appliqué des objets de stratégie de groupe** et vérifiez que les noms des objets de stratégie de groupe créés précédemment sont dans la liste des stratégies appliquées. 

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
    
5.  Vérifiez que la valeur de l’entrée de nom de l’Application est correcte pour le client que vous utilisez, puis vérifiez que la valeur DSCP et le Port Local entrées reflètent les paramètres de l’objet de stratégie de groupe.

## <a name="validate-qos-by-analyzing-teams-traffic-on-the-network"></a>Valider la qualité de service en analysant les équipes le trafic sur le réseau

La valeur DSCP définie par l’objet de stratégie de groupe doit être présent à partir de l’appelant vers l’appelé dans l’ordre de qualité de service être efficaces. En regardant le trafic généré par le client d’équipes, vous pouvez vérifier que la valeur DSCP n’est pas modifiée ou supprimée lorsque le trafic de la charge de travail des équipes traverse le réseau. 

De préférence, vous capturez le trafic réseau à la sortie. Vous pouvez utiliser la mise en miroir de port sur un commutateur ou un routeur pour cela.

### <a name="use-network-monitor-to-verify-dscp-values"></a>Utilisez le Moniteur réseau pour vérifier les valeurs DSCP

Le Moniteur réseau est un outil que vous pouvez [télécharger à partir de Microsoft](https://www.microsoft.com/download/4865) pour analyser le trafic réseau.

1.  Sur l’ordinateur exécutant le Moniteur réseau, connectez-vous au port qui a été configuré pour capturer les paquets de début et de la mise en miroir de port. 

2.  Émettre un appel à l’aide de la Skype pour client d’entreprise. Assurez-vous que le support a été établie avant de raccrocher l’appel. 

3.  Arrêtez la capture.

4. Dans le champ de **Filtre d’affichage** , utilisez l’adresse IP source de l’ordinateur qui effectue l’appel et affiner le filtre en définissant la valeur DSCP 46 (hex d’arrêt 0xb8) comme critères de recherche, comme illustré dans l’exemple suivant :

    Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8 

    ![Capture d’écran de la boîte de dialogue filtre d’affichage dans le Moniteur réseau, affichant des filtres à appliquer.] (media/Qos-in-Teams-Image4.png "Capture d’écran de la boîte de dialogue filtre d’affichage dans le Moniteur réseau, affichant des filtres à appliquer.")

5.  Sélectionnez **Appliquer** pour activer le filtre.

6.  Dans la fenêtre de **Cadre résumé** , sélectionnez le premier paquet UDP.

7.  Dans la fenêtre **Détails de la trame** , développez l’élément de liste IPv4 et notez la valeur à la fin de la ligne qui commence par **le marquage DSCP**. 

    ![Capture d’écran de la boîte de dialogue Détails de l’image dans le Moniteur réseau, mise en surbrillance de paramètres DSCP.] (media/Qos-in-Teams-Image5.png "Capture d’écran de la boîte de dialogue Détails de l’image dans le Moniteur réseau, mise en surbrillance de paramètres DSCP.")

Dans cet exemple, la valeur DSCP est définie à 46. Cela est correct, car le port source utilisé est 50019, qui indique qu’il s’agit d’une charge de travail voix. 

Répétez cette vérification pour chaque charge de travail qui a été marquée par l’objet de stratégie de groupe. 
