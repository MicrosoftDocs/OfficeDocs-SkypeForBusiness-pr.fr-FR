---
title: Menaces fréquentes pour la sécurité dans l’informatique moderne
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/22/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
description: Skype pour Business Server 2015 étant un système de communication d’entreprise, vous devez être conscient des attaques de sécurité courantes qui pourraient affecter son infrastructure et les communications.
ms.openlocfilehash: 351e609ed06ecc84f9417368ac54b7c6424ca01d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="common-security-threats-in-modern-day-computing"></a>Menaces fréquentes pour la sécurité dans l’informatique moderne
 
Skype pour Business Server 2015 étant un système de communication d’entreprise, vous devez être conscient des attaques de sécurité courantes qui pourraient affecter son infrastructure et les communications.
  
## <a name="compromised-key-attack"></a>Attaque par clé compromise

Une clé est un code ou un nombre secret utilisé pour chiffrer, déchiffrer ou valider des informations confidentielles. Deux clés de l’infrastructure à clé publique (PKI) sont particulièrement sensibles :
  
- la clé privée que possède chaque détenteur de certificat ;
    
- la clé de session, utilisée après l’identification et l’échange de clé de session entre les partenaires communiquant entre eux.
    
Une attaque par clé compromise se produit lorsqu’un intrus parvient à identifier la clé privée ou la clé de session. Lorsque l’intrus parvient à déterminer la clé, il s’en sert pour déchiffrer des données chiffrées, à l’insu de l’expéditeur des données.
  
Skype pour Business Server utilise les fonctionnalités de l’infrastructure à clé publique dans le système d’exploitation Windows pour protéger les données de clé utilisées pour le cryptage pour les connexions de Transport Layer Security (TLS). Les clés utilisées pour le chiffrement multimédia sont échangées via des connexions TLS.
  
## <a name="network-denial-of-service-attack"></a>Attaque réseau par déni de service

L’attaque par déni de service se produit lorsque l’attaquant empêche l’utilisation de normal du réseau et les fonctions par les utilisateurs valides. Pour ce faire, elle inonde le service avec des demandes légitimes qui submergent l’utilisation du service par les utilisateurs légitimes. Lors d’une attaque de ce type, la personne malveillante peut :
  
- envoyer des données non valides à des applications et des services exécutés sur le réseau faisant l’objet de l’attaque, afin de perturber leur exécution normale ;
    
- envoyer un volume de trafic important, de manière à surcharger le système jusqu’à ce que celui-ci cesse de fonctionner ou nécessite beaucoup de temps pour répondre aux demandes légitimes ;
    
- masquer les signes d’attaque ;
    
- empêcher les utilisateurs d’accéder aux ressources réseau.
    
## <a name="eavesdropping-sniffing-snooping"></a>Attaque par écoute (Eavesdropping)

Écoute clandestine peut se produire lorsqu’un attaquant parvient à accéder au chemin d’accès de données dans un réseau et a la possibilité de contrôler et de lire le trafic. Il s’agit également d’orsnooping de calledsniffing. Si le trafic consiste en du texte simple, l’intrus peut lire le trafic lorsqu’il accède au chemin d’accès des données. Par exemple, une attaque peut être lancée en contrôlant un routeur sur le chemin de données. 
  
La recommandation par défaut et le paramètre au niveau du trafic Skype pour Business Server consiste à utiliser des mutual TLS (MTLS) entre les serveurs de confiance et TLS à partir du client au serveur. Cette mesure de protection rend ce type d’attaque difficile, voire impossible, durant le laps de temps pendant lequel une conversation donnée peut être attaquée. Le protocole TLS authentifie toutes les parties et chiffre le trafic. Ceci n’empêche pas les attaques par écoute, mais l’intrus ne peut pas lire le trafic à moins que le chiffrement ne soit rompu.
  
Le protocole TURN (Traversal Using Relay NAT) n’exige pas que le trafic soit chiffré. Les informations acheminées sont protégées par l’intégrité des messages. Bien qu’elles puissent faire l’objet d’une attaque par écoute, les informations acheminées (autrement dit, les adresses IP et le port) peuvent être extraites directement, en observant simplement les adresses source et de destination des paquets. Le service Edge A/V s’assure que les données sont valides en vérifiant l’intégrité du message à l’aide d’une clé dérivée de plusieurs éléments, dont un mot de passe TURN, qui n’est jamais transmise en texte en clair. Si le protocole SRTP (Secure Real Time Protocol) est utilisé, le trafic multimédia est également chiffré.
  
## <a name="identity-spoofing-ip-address-spoofing"></a>Usurpation d’identité (usurpation d’adresse IP)

L’usurpation d’identité se produit lorsque le pirate détermine et utilise une adresse IP d’un réseau, un ordinateur ou un composant réseau sans être autorisé au pour faire. Si l’attaque réussit, l’intrus peut opérer comme s’il était l’utilisateur habituellement identifié par l’adresse IP. Dans le contexte de Skype pour le serveur de l’entreprise, cette situation intervient uniquement si un administrateur a effectué les opérations suivantes :
  
- configuré des connexions qui prennent uniquement en charge le protocole TCP (Transmission Control Protocol), ce qui n’est pas recommandé car les communications TCP ne sont pas chiffrées ;
    
- marqué les adresses IP de ces connexions en tant qu’hôtes approuvés.
    
Ce problème est moins grave pour les connexions TLS (Transport Layer Security), car TLS authentifie toutes les parties et chiffre le trafic. L’utilisation du protocole TLS empêche une personne malveillante d’usurper une adresse IP sur une connexion spécifique (par exemple, les connexions Mutual TLS). Mais un utilisateur malveillant pourrait usurper toujours de l’adresse du serveur DNS que Skype pour Business Server utilise. Toutefois, étant donné que l’authentification dans Skype pour entreprises est effectuée avec des certificats, un attaquant devrait pas un certificat valide est requis pour usurper une des parties à la communication.
  
## <a name="man-in-the-middle-attack"></a>Attaque de l’intercepteur (« man-in-the-middle »)

Une attaque man-in-the-middle se produit lorsqu’un agresseur redirige la communication entre deux utilisateurs par le biais de l’ordinateur pirate sans la connaissance des deux utilisateurs communiquent. L’intrus peut surveiller et lire le trafic avant de l’acheminer vers le destinataire concerné. Chacun des utilisateurs envoie et reçoit du trafic vers/de l’intrus, alors qu’il pense communiquer avec l’utilisateur concerné uniquement. Cela peut se produire si une personne malveillante modifie les services de domaine Active Directory pour ajouter son serveur en tant que serveur approuvé, ou si elle modifie DNS (Domain Name System) pour faire en sorte que les clients se connectent au serveur via l’ordinateur de l’intrus à l’origine de l’attaque. Une attaque de l’intercepteur peut également affecter le trafic multimédia entre deux clients. Toutefois, dans Skype pour audio de point à point Business Server, la vidéo et le partage d’application, le flux de données est cryptés avec SRTP, à l’aide de clés de chiffrement qui sont négociées entre les homologues qui utilisent le protocole SIP (Session Initiation) sur TLS. Les serveurs tels que le serveur de conversation de groupe utilisent le protocole HTTPS pour sécuriser le trafic.
  
## <a name="rtp-replay-attack"></a>Attaque par relecture RTP

Une attaque de relecture se produit lorsqu’une transmission media valide entre les deux parties est interceptée et retransmise à des fins malveillantes. SRTP utilisé dans le cadre d’un protocole de signalisation sécurisé protège les transmissions des attaques par relecture en activant le récepteur conserve un index de paquets de protocole RTP déjà reçus et comparer chaque nouveau paquet avec ceux déjà répertoriés dans l’index.
  
## <a name="spim"></a>Messages instantanés indésirables (Spim)

Messages instantanés indésirables est messages instantanés commerciaux non sollicités ou abonnement de présence demandes. Tandis que pas en soi un compromis du réseau, il est ennuyeux dans le moins permet de réduire la disponibilité des ressources et la production et peut éventuellement aboutir à un compromis du réseau. Un exemple est les utilisateurs spimming eux en envoyant des requêtes. Les utilisateurs peuvent bloquer mutuellement pour éviter ce problème, mais avec la fédération, si une attaque spim coordonnée est établie, il peut être difficile à surmonter, sauf si vous désactivez la fédération pour le partenaire.
  
## <a name="viruses-and-worms"></a>Virus et vers

Un virus est une unité de code qui vise à reproduire des unités de code identiques. Pour fonctionner, un virus a besoin d’un hôte, comme un fichier, un e-mail ou un programme. Aworm est une unité de code qui vise à reproduire des unités de code supplémentaire, semblable, mais il n’est pas nécessaire d’un hôte. Les virus et les vers principalement s’affichent pendant les transferts de fichiers entre clients ou lorsque les URL sont envoyées à d’autres utilisateurs. Si un virus se trouve sur votre ordinateur, il peut, par exemple, utiliser votre identité et envoyer des messages instantanés à votre place.
  
## <a name="personally-identifiable-information"></a>Informations d’identification personnelle

Skype pour Business Server a le potentiel de divulguer des informations sur un réseau public qui peut être en mesure d’être liées à un individu. Ces informations appartiennent à deux catégories :
  
- **Données de présence amélioré** Les données de présence améliorée sont informations qu’un utilisateur peut choisir de partager ou non sur une liaison à un partenaire fédéré ou avec des contacts au sein d’une organisation. Elles ne sont pas partagées avec les utilisateurs d’un réseau public de messagerie instantanée. Selon les stratégies de groupe en vigueur et la configuration du client, l’administrateur système peut contrôler ces informations. Dans Skype pour Business Server, le mode de confidentialité de présence améliorée peut être configuré pour un utilisateur individuel empêcher Skype pour les utilisateurs professionnels pas sur la liste de Contacts de l’utilisateur de voir les informations de présence de l’utilisateur. Mode de confidentialité de présence améliorée n’empêche pas les utilisateurs de Microsoft Office Communicator 2007 et Microsoft Office Communicator 2007 R2 à partir de l’affichage des informations de présence d’un utilisateur. Pour plus d’informations sur le déploiement du client et la présence, consultez le [Plan pour la messagerie instantanée et de présence dans Skype pour Business Server 2015](../../plan-your-deployment/instant-messaging-and-presence.md)et [déployer les clients de Skype pour Business Server 2015](../../deploy/deploy-clients/deploy-clients.md) .
    
- **Données obligatoires** Données obligatoires est nécessaires au bon fonctionnement du serveur ou du client et ne sont pas sous le contrôle de l’administration du système ou du client. Il s’agit d’informations qui sont nécessaires à un serveur ou d’un niveau de réseau aux fins de la maintenance de routage, l’état et signalisation.
    
Les tableaux suivants répertorient les données exposées sur un réseau public.
  
**Données de présence améliorée**

|**Données communiquées**|**Paramètres possibles**|
|:-----|:-----|
|Données personnelles  <br/> |Nom, Fonction, Société, Adresse électronique, Fuseau horaire  <br/> |
|Numéros de téléphone  <br/> |Bureau, Mobile, Domicile  <br/> |
|Informations de calendrier  <br/> |Libre/Occupé(e), notification d’absence du bureau, détails de réunion (pour les personnes ayant accès à votre calendrier)  <br/> |
|Statut de présence  <br/> |Absent(e), Disponible, Occupé(e), Ne pas déranger, Hors connexion  <br/> |
   
**Données obligatoires**

|**Données communiquées**|**Exemples d’informations**|
|:-----|:-----|
|Adresse IP  <br/> |Adresse réelle de l’ordinateur ou adresse traduite via NAT  <br/> |
|URI SIP  <br/> |jeremylos@litwareinc.com  <br/> |
   

