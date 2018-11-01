---
title: 'Lync Server 2013 : Déplacement d’utilisateurs vers Voix Entreprise'
TOCTitle: Déplacement d’utilisateurs vers Voix Entreprise
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412758(v=OCS.15)
ms:contentKeyID: 49298380
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déplacement d’utilisateurs vers Voix Entreprise dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Si vous déplacez des utilisateurs d’une infrastructure téléphonique PBX existante vers Voix Entreprise, le processus de déploiement comprend certaines étapes qui ne font pas partie du processus de planification déjà décrit dans [Planification de Voix Entreprise dans Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md). Pour plus d’informations sur la migration des utilisateurs à partir d’un déploiement antérieur de Voix Entreprise, reportez-vous aux documents de migration inclus dans votre support d’installation.

Le processus de déplacement d’utilisateurs à partir d’une infrastructure téléphonique existante vers Voix Entreprise comprend les étapes suivantes :

1.  Indiquer les numéros de téléphone principaux.

2.  Activer les utilisateurs pour Voix Entreprise.

3.  Préparer les plans de numérotation des utilisateurs.

4.  Planifier des stratégies de voix utilisateur.

5.  Planifier des itinéraires téléphoniques.

6.  Configurer le système PBX ou la jonction SIP pour rediriger les appels destinés aux utilisateurs activés pour Voix Entreprise.

7.  Déplacer des utilisateurs vers la messagerie unifiée messagerie unifiée Exchange (recommandé).

Cette rubrique décrit la planification nécessaire à chacune de ces étapes.

## Étape 1 : indiquer les numéros de téléphone principaux

Voix Entreprise intègre la voix à d’autres médias de messagerie ; par exemple, lorsqu’un appel entrant arrive sur le serveur, celui-ci mappe le numéro sur l’URI SIP de l’utilisateur, puis dirige l’appel vers tous les points de terminaison clients associés à cet URI SIP. Ce processus requiert que chaque utilisateur soit associé à un numéro de téléphone principal.

Un numéro de téléphone principal doit :

  - être globalement unique ou, dans le cas de numéros de postes internes, unique dans l’entreprise ;

  - appartenir à l’entreprise et y être routable. Les numéros personnels ne doivent pas être utilisés.

Les utilisateurs de l’entreprise peuvent avoir un ou plusieurs numéros de téléphone répertoriés à leur nom dans les services de domaine Active Directory). Tous les numéros de téléphone associés à un utilisateur particulier peuvent être affichés ou modifiés dans la feuille de propriétés de cet utilisateur, dans le composant logiciel enfichable Utilisateurs et ordinateurs Active Directory.

La zone **Numéro de téléphone** située sous l’onglet **Général** de la boîte de dialogue **Propriétés de l’utilisateur** doit contenir le numéro professionnel principal de l’utilisateur. Ce numéro est habituellement indiqué comme numéro de téléphone principal de l’utilisateur.

Certains utilisateurs peuvent avoir des exigences particulières (par exemple, un cadre qui veut que tous les appels entrants soient routés par le biais d’un assistant administratif), mais de telles exceptions doivent se limiter à des cas où le besoin est précis et essentiel.

Une fois qu’un numéro principal est choisi, il doit être :

  - normalisé au format E.164, si possible ;

  - copié dans l’attribut Active Directory **msRTCSIP-line**.
    
    > [!NOTE]  
    > <strong>Coexistence avec le contrôle d’appel distant</strong><br />
    Le contrôle d’appel distant est la capacité à utiliser Lync Server pour surveiller et contrôler un téléphone de bureau PBX. Le contrôle est acheminé par le biais du serveur, qui joue le rôle de passerelle vers le système PBX. Même si vous ne pouez pas configurer un utilisateur à la fois pour le contrôle d’appel distant et Voix Entreprise, le paramètre URI de ligne spécifie un numéro de téléphone principal de l’utilisateur dans un cas comme dans l’autre.<br />
    Si vous disposez d’une infrastructure PBX existante et que vous voulez que certains utilisateurs sélectionnés continuent à l’utiliser, vous pouvez introduire Voix Entreprise de manière incrémentielle dans votre organisation. Pour plus d’informations sur ce scénario de déploiement, reportez-vous à <a href="lync-server-2013-direct-sip-deployment-options.md">Options de déploiement SIP direct dans Lync Server 2013</a> dans la documentation de planification.<br />
    Dans les versions précédentes, vous pouviez activer à la fois le contrôle d’appel distant et Voix Entreprise pour un utilisateur, mais uniquement si vous configuriez aussi l’utilisateur pour le branchement double, une fonction dans laquelle un appel entrant sonne simultanément sur le téléphone PBX d’un utilisateur et Communicator. Dans Lync Server 2010, le branchement double n’est pas pris en charge.

Il existe trois façons de renseigner l’attribut **msRTCSIP-line** :

  - serveur MIIS (Microsoft Identity Integration Server) (recommandé) ;

  - la page **Utilisateurs** dans le Panneau de configuration Lync Server.

Lorsque de nombreux numéros de téléphone doivent être traités, un script personnalisé développé par votre organisation constitue la meilleure solution. En fonction de la façon dont votre organisation affiche les numéros de téléphone dans les services de domaine Active Directory, le script devra peut-être normaliser les numéros de téléphone principaux au format E.164 avant de les copier dans l’attribut **msRTCSIP-line**.

  - Si votre organisation gère tous les numéros de téléphone dans les services de domaine Active Directory sous un seul format et si ce format est E.164, il suffit que votre script écrive chaque numéro de téléphone principal dans l’attribut **msRTCSIP-line**.

  - Si votre organisation gère tous les numéros de téléphone dans les services de domaine Active Directory sous un seul format, mais que ce format n’est pas E.164, votre script doit définir une règle de normalisation appropriée pour convertir les numéros de téléphone principaux sous leur format existant au format E.164 avant de les écrire dans l’attribut **msRTCSIP-line**.

  - Si votre organisation n’applique pas de format standard pour les numéros de téléphone dans les services de domaine Active Directory, votre script doit définir des règles de normalisation appropriées pour convertir les numéros de téléphone principaux au format E.164 avant de les écrire dans l’attribut **msRTCSIP-line**.

Votre script doit également insérer le préfixe  **Tel:** avant chaque numéro principal avant de l’écrire dans l’attribut **msRTCSIP-line**.

Le format attendu du numéro spécifié dans cet attribut est :

  - Tel:+14255550100;ext=50100.

  - Tel:5550100 (pour les postes uniques à l’échelle de l’entreprise)
    
    > [!IMPORTANT]  
    > La normalisation effectuée par le Service de carnet d’adresses ne remplace, ni n’élimine le besoin de normaliser le numéro de téléphone principal de chaque utilisateur dans les services de domaine Active Directory, car le Service de carnet d’adresses n’a pas accès à ces services et ne peut, par conséquent, pas copier les numéros principaux dans l’attribut <strong>msRTCSIP-line</strong>.

## Étape 2 : activer les utilisateurs pour Voix Entreprise

Une fois que vous avez identifié les utilisateurs à activer, aucune planification spéciale n’est requise pour effectuer cette étape.

## Étape 3 : préparer les plans de numérotation des utilisateurs.

Les utilisateurs activés pour Voix Entreprise ne pourront pas passer d’appel sur le réseau téléphonique commuté sans la mise en place de plans de numérotation. Un plan de numérotation est un ensemble nommé de règles de normalisation qui convertissent des numéros de téléphone pour un emplacement, un utilisateur individuel ou un objet contact nommé en un format standard (E.164) à des fins d’autorisation téléphonique et de routage des appels. Les règles de normalisation définissent la façon dont les numéros de téléphone exprimés en divers formats sont acheminés vers chaque emplacement, utilisateur ou objet contact.

Pour plus d’informations sur la préparation de plans de numérotation, reportez-vous à [Plans de numérotation et règles de normalisation dans Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).

## Étape 4 : planifier des stratégies de voix utilisateur

Les paramètres de classe de service utilisateur du système PBX hérité, tels que l’autorisation à passer des appels longue distance ou internationaux depuis les téléphones de la société, doivent être reconfigurés en tant que stratégies VoIP pour les utilisateurs déplacés vers Voix Entreprise. Pour plus d’informations sur la planification et la création de stratégies pour Voix Entreprise, reportez-vous à [Stratégies de voix dans Lync Server 2013](lync-server-2013-voice-policies.md).

## Étape 5 : planifier des itinéraires téléphoniques sortants

Les itinéraires téléphoniques spécifient comment Lync Server traite les appels sortants passés par les utilisateurs de Voix Entreprise. Lorsqu’un utilisateur compose un numéro, le serveur, si nécessaire, normalise la chaîne de numérotation au format E.164 et tente de le mettre en correspondance avec un URI SIP. Si le serveur ne parvient pas à établir de correspondance, il applique la logique de routage des appels sortants en fonction du numéro. La dernière étape de la définition de cette logique consiste à créer un itinéraire téléphonique nommé distinct pour chaque ensemble de numéros de téléphone de destination répertorié dans chaque plan de numérotation.

Pour plus d’informations sur la planification des itinéraires téléphoniques, reportez-vous à [Itinéraires des communications vocales dans Lync Server 2013](lync-server-2013-voice-routes.md).

## Étape 6 : configurer le système PBX ou la jonction SIP pour rediriger les appels destinés aux utilisateurs de Voix Entreprise

Les utilisateurs qui étaient auparavant hébergés sur un système PBX traditionnel ou une connexion de jonction SIP auprès d’un fournisseur de services de téléphonie Internet conservent leurs numéros de téléphone après le déplacement. La seule exigence est que le système PBX ou la jonction SIP doit être reconfiguré après le déplacement pour acheminer les appels entrants destinés aux utilisateurs de Voix Entreprise vers le serveur de médiation.

## Étape 7 : déplacer des utilisateurs vers la messagerie unifiée Exchange (recommandé)

Le déplacement d’utilisateurs vers la messagerie unifiée Exchange comprend les tâches suivantes :

  - Configurer la messagerie unifiée Exchange et Lync Server afin qu’ils fonctionnent ensemble.

  - Activer les utilisateurs pour le répondeur automatique de la messagerie unifiée Exchange et Outlook Voice Access. Cette tâche est effectuée sur le serveur de messagerie unifiée Exchange. Pour plus d’informations, reportez-vous à la bibliothèque TechNet Exchange Server 2010 à l’adresse [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372).

