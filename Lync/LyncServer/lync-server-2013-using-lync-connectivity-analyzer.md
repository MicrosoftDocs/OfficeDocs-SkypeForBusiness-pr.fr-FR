---
title: Utilisation de l’Analyseur de connectivité Lync
TOCTitle: Utilisation de l’Analyseur de connectivité Lync
ms:assetid: 954953fb-0c7a-4fd5-8acd-68ecb59b20af
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ907302(v=OCS.15)
ms:contentKeyID: 53095476
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation de l’Analyseur de connectivité Lync

 

_**Dernière rubrique modifiée :** 2016-12-08_

L’Analyseur de connectivité Microsoft Lync aide les administrateurs de Lync à déterminer si le déploiement et la configuration de leur environnement Office 365 ou Lync Server local remplissent les conditions requises pour prendre en charge les connexions à partir d’applications application Lync du Windows Store et Lync sur les appareils mobiles.

L’Analyseur de connectivité Lync tente de se connecter à votre serveur Lync Server local ou Skype Entreprise Online à l’aide des mêmes services et protocoles que ceux utilisés par les application Lync du Windows Store et applications mobiles Lync. Vous pouvez exécuter les tests de connexion par le biais de votre réseau interne ou d’un réseau externe qui se connecte à Lync Server ou Skype Entreprise Online. L’Analyseur de connectivité Lync fournit un rapport contenant des informations détaillées sur chaque étape de connexion, afin de vous aider à valider votre configuration et résoudre les problèmes de connexion.

L’Analyseur de connectivité Lync teste les composants suivants de Lync Server :

  - Service de découverte automatique

  - Broker d’authentification (portée)

  - Service de mobilité (MCX)

  - Service de mobilité (UCWA)

  - Service de ticket Web

L’Analyseur de connectivité Lync teste la configuration des autres composants suivants :

  - Publication des enregistrements DNS pour les URL de découverte automatique

  - Certificats

  - Serveurs proxy

Vous pouvez télécharger l’Analyseur de connectivité de Lync à partir du Centre de téléchargement Microsoft à l’adresse <http://go.microsoft.com/fwlink/?linkid=277056>.

## Pour analyser votre connectivité

1.  Entrez les informations d’identification d’un compte Lync valide (compte Lync local ou compte Office 365Lync) qui sera utilisé par l’outil pour tester la connexion :
    
      - Dans **Type de compte Lync**, sélectionnez **Office 365** ou **Local**.
    
      - Dans **SIP URI**, entrez l’adresse de connexion SIP de la connexion Lync au format <strong>utilisateur@domaine.com</strong>.
    
      - Dans **Mot de passe**, entrez le mot de passe associé à ce compte.
    
      - Dans **User name (optional)**, entrez un nom d’utilisateur (également appelé nom d’utilisateur principal) le cas échéant. Si le nom d’utilisateur et l’URI SIP sont identiques, il n’est pas nécessaire d’entrer un nom d’utilisateur. S’ils sont différents, entrez le nom d’utilisateur au format <strong>utilisateur@domaine.com</strong> ou **domaine\\utilisateur**, selon le cas.
    
      - **Network access**, sélectionnez **From inside my organization** si vous exécutez l’Analyseur de connectivité Lync à partir d’un ordinateur connecté à votre réseau interne. Sinon, sélectionnez **External (Internet)**. L’Analyseur de connectivité Lync effectue toujours des tests internes et externes, mais le fait de préciser si vous vous trouvez à l’intérieur ou à l’extérieur de votre propre réseau l’aide à interpréter si certaines défaillances sont attendues.
    
      - Dans **Client**, spécifiez si vous souhaitez effectuer des tests de connectivité pour les applications **Lync Windows Store**, **Lync Mobile 2010** ou **Lync Mobile 2013**.
    
      - Sous **Découverte du serveur**, sélectionnez le type de test à effectuer :
        
          - Si vous souhaitez que l’outil découvre le serveur Lync automatiquement, sélectionnez **Automatique**.
        
          - Si vous souhaitez que l’outil ignore le test de découverte automatique, ou si vous connaissez le nom du serveur auquel vous voulez vous connecter, sélectionnez **Adresse d'utilisation manuelle :** puis, spécifiez le nom de domaine complet du serveur Lync, par exemple **lync.company.com**.

2.  (Facultatif) Sous **Fichier journal**, activez la case à cocher si vous voulez créer un fichier journal dans le chemin d'accès spécifié. Si la journalisation est activée, cliquez sur **Effacer** pour effacer le fichier journal, cliquez sur **Ouvrir** pour ouvrir et consulter le fichier journal, cliquez sur **Messagerie** pour ouvrir un message électronique afin d'envoyer les résultats à votre équipe de support (vous devez joindre manuellement le fichier journal à partir du chemin d'accès spécifié).

3.  Cliquez sur **Start**.

La figure suivante montre un exemple de résultat de l’Analyseur de connectivité Lync.

**Analyseur de connectivité Lync**

![Capture d’écran de l’Analyseur de connectivité Lync](images/JJ907302.a7cc0abe-fac2-4691-a7d8-9ffef59cdee5(OCS.15).png "Capture d’écran de l’Analyseur de connectivité Lync")

## Composants testés par l’Analyseur de connectivité Lync

L’Analyseur de connectivité Lync tente de découvrir le serveur Lync et d’établir une connexion en effectuant les mêmes étapes que celles suivies par les application Lync du Windows Store et les applications mobiles Lync. Il effectue les tests comme décrit dans cette section.

Si **Automatic discovery** est sélectionné, l’Analyseur de connectivité Lync effectue les opérations suivantes :

  - Il interroge le système de noms de domaine (DNS, Domain Name Service) afin de connaître les URL de découverte automatique.

  - Il tente de procéder à la découverte à l’aide du canal interne sécurisé. Par exemple **HTTPS://lyncdiscoverinternal.company.com/**.

  - Il tente de procéder à la découverte à l’aide du canal interne non sécurisé. Par exemple **HTTP://lyncdiscoverinternal.company.com/**.

  - Il tente de procéder à la découverte à l’aide du canal externe sécurisé. Par exemple **HTTPS://lyncdiscover.company.com/**.

  - Il tente de procéder à la découverte à l’aide du canal externe non sécurisé. Par exemple **HTTP://lyncdiscover.company.com/**.

Si **Use the following server discovery address** est sélectionné, l’Analyseur de connectivité Lync effectue les opérations suivantes :

  - Il interroge le système DNS afin de connaître le nom de domaine complet du serveur.

  - Il tente de procéder à la découverte à l’aide du canal sécurisé. Par exemple **HTTPS://nom\_domaine\_complet\_du\_serveur/**.

  - Il tente de procéder à la découverte à l’aide du canal non sécurisé. Par exemple **HTTP://nom\_domaine\_complet\_du\_serveur/**.

Si **Lync Windows Store app** est sélectionné sous **Test the requirements for**, l’Analyseur de connectivité Lync effectue les opérations suivantes :

  - Il vérifie que le service de ticket web est disponible et teste l’authentification des informations d’identification de compte Lync.

  - Il vérifie que le service Broker d’authentification (portée) est disponible.

Si **Lync Mobile 2010 App** est sélectionné sous **Client**, l’Analyseur de connectivité Lync effectue les opérations suivantes :

  - Il vérifie que le service de ticket web est disponible et teste l’authentification des informations d’identification de compte Lync.

  - Il vérifie que le service de mobilité (MCX) est disponible.

Si **Lync Mobile 2013 App** est sélectionné sous **Client**, l’Analyseur de connectivité Lync effectue les opérations suivantes :

  - Il vérifie que le service de ticket web est disponible et teste l’authentification des informations d’identification de compte Lync.

  - Il vérifie que le service de mobilité (UCWA) est disponible.

Lors de l’exécution de ces tests, l’Analyseur de connectivité Lync valide les certificats installés sur Lync Server, les équilibreurs de charge matérielle, les serveurs proxy et l’ordinateur sur lequel vous exécutez les tests.

## Autres ressources

Microsoft propose également l’Analyseur de connectivité à distance Microsoft, un outil de test de connectivité basé sur le web disponible à l’adresse <https://testconnectivity.microsoft.com/>. L’Analyseur de connectivité Lync et l’Analyseur de connectivité à distance diffèrent des manières suivantes :

  - L’Analyseur de connectivité à distance peut tester la connectivité pour Microsoft Exchange et Outlook, en plus de Microsoft Lync.

  - L’Analyseur de connectivité à distance effectue la connexion SIP, tandis que l’Analyseur de connectivité Lync valide uniquement les informations d’identification de compte, sans procéder à la connexion.

  - L’Analyseur de connectivité à distance teste uniquement les connexions provenant de l’extérieur de votre réseau d’entreprise, car il s’exécute à partir d'un serveur Web public.

  - L’Analyseur de connectivité à distance ne teste pas la disponibilité du Broker d’authentification (portée) et des services de mobilité (MCX) et de ticket Web.

  - L’analyseur de connectivité Lync teste le service de découverte automatique.

  - L’Analyseur de connectivité à distance peut se connecter à n’importe quelle version de Lync Server, alors que l’Analyseur de connectivité Lync peut uniquement se connecter à Lync Server 2010 avec les Mises à jour cumulatives pour Lync Server 2010 de février 2012 (au minimum) ou la version la plus récente de Lync Server.

La documentation suivante décrit les conditions requises et les procédures de déploiement et de configuration de Lync Server pour la prise en charge des application Lync du Windows Store et des clients mobiles Lync :

  - [Déploiement des clients et appareils dans Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md)

  - [Planification de la mobilité dans Lync Server 2013](lync-server-2013-planning-for-mobility.md)

  - [Déploiement de la mobilité dans Lync Server 2013](lync-server-2013-deploying-mobility.md)

