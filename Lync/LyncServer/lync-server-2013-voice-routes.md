---
title: 'Lync Server 2013 : Itinéraires des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e46b4074d41d2ac79dfe63bc99411a7aba72a88c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-routes-in-lync-server-2013"></a>Itinéraires des communications vocales dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-22_

Les itinéraires d’appels spécifient comment Lync Server gère les appels sortants placés par des utilisateurs d’Enterprise Voice. Lorsqu’un utilisateur compose un numéro, le serveur frontal normalise la chaîne de numérotation au format E. 164, si nécessaire, et tente de correspondre à un URI SIP. Si le serveur ne parvient pas à établir de correspondance, il applique la logique de routage des appels sortants en fonction du numéro. La dernière étape de la définition de cette logique consiste à créer un itinéraire téléphonique nommé distinct pour chaque ensemble de numéros de téléphone de destination répertorié dans chaque plan de numérotation.

Avant de définir des itinéraires d’appels sortants, vous devez effectuer les étapes suivantes :

  - Déployer une ou plusieurs jonctions.

  - Créer des plans de numérotation selon les besoins des sites, des personnes, ainsi que des objets Contact.

  - Créer des enregistrements d’utilisation PSTN (réseau téléphonique commuté).

En outre, pour activer le routage des appels sortants, vous devez créer et affecter une ou plusieurs stratégies de voix. Vous pouvez effectuer cette tâche avant ou après la définition des itinéraires des appels sortants.

Pour chaque itinéraire, vous devez indiquer :

  - un nom sous lequel l’itinéraire peut être facilement identifié ;

  - une description facultative pour les cas où le nom seul peut ne pas être suffisant pour décrire l’itinéraire ;

  - le modèle correspondant à l’expression régulière qui identifie les numéros de téléphone de destination auxquels l’itinéraire est appliqué, ainsi que les exceptions auxquelles le modèle ne doit pas être appliqué ;

  - une ou plusieurs jonctions que vous souhaitez affecter à l’itinéraire ;

  - les enregistrements d’utilisation PSTN dont doivent disposer les utilisateurs afin d’appeler des numéros qui correspondent à l’expression régulière du numéro de téléphone de destination.

Vous pouvez spécifier des itinéraires d’appels dans le panneau de configuration de Lync Server. Ces itinéraires d’appel remplissent la table de routage du serveur, qui est utilisée par Lync Server pour diriger les appels destinés au RTC.

<div>

## <a name="mn-trunk-support"></a>M:N Prise en charge des jonctions

Lync Server offre une souplesse pour le routage des appels vers PSTN. Un itinéraire des communications vocales spécifie un ensemble de jonctions au PSTN qui peuvent être utilisées pour un appel vocal particulier. Un Trunk associe un serveur de médiation et un numéro de port avec une passerelle PSTN et un numéro de port d’écoute. Cette association logique permet d’associer un serveur de médiation à plusieurs passerelles et de disposer de plusieurs connexions à la même passerelle. Lors de la définition d’un itinéraire d’appel, vous spécifiez les Trunks associés à cet itinéraire, mais vous ne spécifiez pas les serveurs de médiation associés à l’itinéraire. Pour créer des Trunks en définissant les relations entre les serveurs de médiation et les passerelles RTC, PBX IP et contrôleurs de frontière de session (SBCs), utilisez le générateur de topologie.

</div>

<div>

## <a name="least-cost-routing"></a>Routage à moindre coût

La possibilité de spécifier les jonctions vers lesquelles différents numéros sont routés permet de déterminer les itinéraires qui offrent les coûts les plus bas et de les mettre en œuvre en conséquence. La règle générale concernant la sélection des jonctions consiste à choisir celle possédant la passerelle la plus proche du numéro de destination afin de réduire les coûts des appels longue distance. Par exemple, si vous vous trouvez à New York et que vous appelez un numéro à Rome, vous transférerez l’appel via le réseau IP vers la jonction avec la passerelle de votre bureau romain, ne subissant ainsi que le coût d’un appel local.

Voici un exemple d’utilisation du routage à moindre coût : Fabrikam décide d’autoriser les utilisateurs allemands à composer des numéros américains à l’aide de la jonction correspondante. Fabrikam veut également configurer le système de manière à ce que tous les appels des utilisateurs du serveur Lync U.S. vers l’Allemagne et les pays/régions adjacents se terminent sur le Trunk avec la passerelle en Allemagne. Ce routage est économique car un appel passé de l’Allemagne vers l’Australie, par exemple, est moins onéreux qu’un appel émis des États-Unis en direction de l’Australie.

</div>

<div>

## <a name="translating-outbound-dial-strings"></a>Conversion des chaînes de numérotation sortantes

Lync Server 2013, à l’instar de ses prédécesseurs, nécessite que toutes les chaînes de numérotation soient normalisées au format E. 164 pour pouvoir exécuter la recherche de numéros inverse (RNL). S’il s’agit de lignes avec passerelles ou d’échangeurs de succursales privées (PBX) qui nécessitent des numéros traduits dans les formats de numérotation locaux, Lync Server 2013 vous permet de créer une ou plusieurs règles qui vous aident à manipuler le numéro appelé (URI de demande) avant de le diriger vers le tronc. Par exemple, vous pouvez rédiger une règle pour supprimer la valeur « +44 » au début de la chaîne de numérotation et la remplacer par « 0144 ».

Avec Lync Server 2013, il est possible de créer une ou plusieurs règles qui vous aident à manipuler le numéro d’appel avant de le diriger vers le Trunk.

Dans la planification de vos Trunks qui associent des passerelles: paires de port avec médiation Server: paires de port, il peut être utile de regrouper les Trunks avec des exigences de numérotation locales similaires, et donc de réduire le nombre de règles de traduction requises et le temps nécessaire pour les écrire.

</div>

<div>

## <a name="configuring-caller-id"></a>Configuration d’un ID d’appelant

Lync Server fournit un moyen de manipuler l’ID de l’appelant pour les appels sortants. Par exemple, si une organisation veut masquer les extensions de numérotation directe des employés et les remplacer par le numéro générique d’entreprise ou de département, un administrateur peut le faire en utilisant le panneau de configuration de Lync Server pour supprimer l’ID de l’appelant et le remplacer par un ID d’appelant différent spécifié. Lors de la planification de votre logique de routage, déterminez les personnes, groupes ou sites pour lesquels vous souhaiterez activer cette option (vous pourriez même l’activer pour l’ensemble des employés).

<div>


> [!NOTE]  
> Pour les appels réacheminés sur le réseau téléphonique commuté, l’ID de l’appelant générique s’affiche à la place de l’ID initial. L’appel peut alors contourner les paramètres de confidentialité ou « Ne pas déranger » éventuellement configurés par l’appelé.



</div>

</div>

<div>

## <a name="additional-routing-logic"></a>Logique de routage supplémentaire

Lors de la création d’itinéraires téléphoniques sortants, vous devez avoir conscience des facteurs suivants susceptibles d’affecter la logique de routage :

  - Lorsqu’un appel est établi sur une limite fédérée, la partie domaine de l’URI permet d’acheminer l’appel vers l’entreprise chargée de l’application de la logique du routage sortant.

  - Si la partie domaine de l’URI demandé ne contient pas de domaine pris en charge pour l’entreprise, le composant de routage sortant sur le serveur ne traite pas l’appel.

  - Si un utilisateur n’est pas activé pour voix entreprise, le serveur applique une autre logique de routage, selon le cas.

  - Si un appel est acheminé vers une passerelle totalement occupée (toutes les lignes de la jonction sont occupées), la passerelle refuse l’appel et la logique de routage des appels sortants le redirige vers l’itinéraire à moindre coût suivant. Vous devez tenir compte de ces éléments, car une passerelle dont la taille est adaptée à un petit bureau à l’étranger (par exemple, Zurich) peut en réalité transporter une quantité considérable de trafic non local pour des appels internationaux vers la Suisse. Si la taille de la passerelle ne convient pas à ce trafic supplémentaire, les appels vers la Suisse peuvent être acheminés via une passerelle située en Allemagne, ce qui augmente les frais téléphoniques.

</div>

</div>

<span> </span>

</div>

</div>

</div>

