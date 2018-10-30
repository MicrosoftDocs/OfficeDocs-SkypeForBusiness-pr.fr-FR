---
title: 'Lync Server 2013 : Itinéraires des communications vocales'
TOCTitle: Itinéraires des communications vocales
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412757(v=OCS.15)
ms:contentKeyID: 49298379
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Itinéraires des communications vocales dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-22_

Les itinéraires téléphoniques spécifient comment Lync Server traite les appels sortants passés par les utilisateurs de Voix Entreprise. Lorsqu’un utilisateur compose un numéro, le serveur frontal normalise si nécessaire la chaîne de numérotation au format E.164 et tente de la faire correspondre à un URI SIP. Si le serveur ne parvient pas à établir de correspondance, il applique la logique de routage des appels sortants en fonction du numéro. La dernière étape de la définition de cette logique consiste à créer un itinéraire téléphonique nommé distinct pour chaque ensemble de numéros de téléphone de destination répertorié dans chaque plan de numérotation.

Avant de définir des itinéraires d’appels sortants, vous devez effectuer les étapes suivantes :

  - Déployer une ou plusieurs jonctions.

  - Créer des plans de numérotation selon les besoins des sites, des personnes, ainsi que des objets Contact.

  - Créer des enregistrements d’utilisation RTC (réseau téléphonique commuté).

En outre, pour activer le routage des appels sortants, vous devez créer et affecter une ou plusieurs stratégies de voix. Vous pouvez effectuer cette tâche avant ou après la définition des itinéraires des appels sortants.

Pour chaque itinéraire, vous devez indiquer :

  - un nom sous lequel l’itinéraire peut être facilement identifié ;

  - une description facultative pour les cas où le nom seul peut ne pas être suffisant pour décrire l’itinéraire ;

  - le modèle correspondant à l’expression régulière qui identifie les numéros de téléphone de destination auxquels l’itinéraire est appliqué, ainsi que les exceptions auxquelles le modèle ne doit pas être appliqué ;

  - une ou plusieurs jonctions que vous souhaitez affecter à l’itinéraire ;

  - les enregistrements d’utilisation RTC dont doivent disposer les utilisateurs afin d’appeler des numéros qui correspondent à l’expression régulière du numéro de téléphone de destination.

Vous pouvez spécifier des itinéraires téléphoniques dans le Panneau de configuration Lync Server. Ces itinéraires renseignent la table de routage du serveur utilisée par Lync Server pour acheminer les appels destinés au réseau commuté.

## M:N Prise en charge des jonctions

Lync Server offre une flexibilité dans la façon dont les appels sont acheminés vers le RTC. Un itinéraire des communications vocales spécifie un ensemble de jonctions au RTC qui peuvent être utilisées pour un appel vocal particulier. Une jonction associe un serveur de médiation et un numéro de port à une passerelle RTC et un numéro de port d’écoute. Cette association logique permet à un serveur de médiation d’être associé à plusieurs passerelles et de disposer de plusieurs connexions à la même passerelle. Lors de la définition d’un itinéraire téléphonique, vous spécifiez les jonctions associées à cet itinéraire, mais vous ne précisez pas les serveurs de médiation qui y sont associés. Pour créer des jonctions en définissant les relations entre des serveurs de médiation et des passerelles RTC, des IP-PBX et des contrôleurs SBC (Session Border Controllers), utilisez le Générateur de topologie.

## Routage à moindre coût

La possibilité de spécifier les jonctions vers lesquelles différents numéros sont routés permet de déterminer les itinéraires qui offrent les coûts les plus bas et de les mettre en œuvre en conséquence. La règle générale concernant la sélection des jonctions consiste à choisir celle possédant la passerelle la plus proche du numéro de destination afin de réduire les coûts des appels longue distance. Par exemple, si vous vous trouvez à New York et que vous appelez un numéro à Rome, vous transférerez l’appel via le réseau IP vers la jonction avec la passerelle de votre bureau romain, ne subissant ainsi que le coût d’un appel local.

Voici un exemple d’utilisation du routage à moindre coût : Fabrikam décide d’autoriser les utilisateurs allemands à composer des numéros américains à l’aide de la jonction correspondante. Fabrikam veut également configurer le système de sorte que tous les appels en provenance des utilisateurs de Lync Server aux États-Unis et destinés à l’Allemagne et aux pays/régions voisins aboutissent sur la jonction dont la passerelle se trouve en Allemagne. Ce routage est économique car un appel passé de l’Allemagne vers l’Australie, par exemple, est moins onéreux qu’un appel émis des États-Unis en direction de l’Australie.

## Conversion des chaînes de numérotation sortantes

Lync Server 2013, comme ses prédécesseurs immédiats, exige que toutes les chaînes de numérotation adoptent le format standard E.164 pour des besoins de recherche de numéros inversée. Pour les jonctions avec des passerelles ou des PBX (Private Branch Exchanges) qui requièrent des numéros convertis dans des formats de numérotation locaux, Lync Server 2013 vous permet de créer une ou plusieurs règles pour faciliter la manipulation du numéro appelé (autrement dit, l’URI de demande) avant de l’acheminer vers la jonction. Par exemple, vous pouvez rédiger une règle pour supprimer la valeur « +44 » au début de la chaîne de numérotation et la remplacer par « 0144 ».

Avec Lync Server 2013, il est possible de créer une ou plusieurs règles pour simplifier la manipulation du numéro appelé avant de l’acheminer vers la jonction.

En planifiant vos jonctions qui associent des paires passerelles:port à des paires serveur de médiation:port, il peut s’avérer utile de regrouper les jonctions ayant des exigences de numérotation locale similaires afin de réduire le nombre de règles de conversion requises et le temps nécessaire pour les rédiger.

## Configuration d’un ID d’appelant

Lync Server permet de manipuler l’ID de l’appelant pour les appels sortants. Par exemple, si une organisation souhaite masquer les numéros de poste direct des employés et les remplacer par le numéro de l’entreprise ou du service générique, un administrateur peut désormais utiliser le Panneau de configuration Lync Server pour supprimer l’ID de l’appelant et le remplacer par un autre ID d’appelant indiqué. Lors de la planification de votre logique de routage, déterminez les personnes, groupes ou sites pour lesquels vous souhaiterez activer cette option (vous pourriez même l’activer pour l’ensemble des employés).

> [!NOTE]  
> Pour les appels réacheminés sur le réseau téléphonique commuté, l’ID de l’appelant générique s’affiche à la place de l’ID initial. L’appel peut alors contourner les paramètres de confidentialité ou « Ne pas déranger » éventuellement configurés par l’appelé.

## Logique de routage supplémentaire

Lors de la création d’itinéraires téléphoniques sortants, vous devez avoir conscience des facteurs suivants susceptibles d’affecter la logique de routage :

  - Lorsqu’un appel est établi sur une limite fédérée, la partie domaine de l’URI permet d’acheminer l’appel vers l’entreprise chargée de l’application de la logique du routage sortant.

  - Si la partie domaine de l’URI demandé ne contient pas de domaine pris en charge pour l’entreprise, le composant de routage sortant sur le serveur ne traite pas l’appel.

  - Si un utilisateur n’est pas activé pour Voix Entreprise, le serveur applique une autre logique de routage, selon le cas.

  - Si un appel est acheminé vers une passerelle totalement occupée (toutes les lignes de la jonction sont occupées), la passerelle refuse l’appel et la logique de routage des appels sortants le redirige vers l’itinéraire à moindre coût suivant. Vous devez tenir compte de ces éléments, car une passerelle dont la taille est adaptée à un petit bureau à l’étranger (par exemple, Zurich) peut en réalité transporter une quantité considérable de trafic non local pour des appels internationaux vers la Suisse. Si la taille de la passerelle ne convient pas à ce trafic supplémentaire, les appels vers la Suisse peuvent être acheminés via une passerelle située en Allemagne, ce qui augmente les frais téléphoniques.

