---
title: Menaces fréquentes pour la sécurité dans l’informatique moderne
ms.reviewer: ''
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
description: Skype pour Business Server étant un système de communications d’entreprise, vous devez être conscient des attaques de sécurité courantes susceptibles d’affecter son infrastructure et les communications.
ms.openlocfilehash: 15c5f71db846ad51fa0df70396cb7ca1252dd4dc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213647"
---
# <a name="common-security-threats-in-modern-day-computing"></a>Menaces fréquentes pour la sécurité dans l’informatique moderne
 
Skype pour Business Server étant un système de communications d’entreprise, vous devez être conscient des attaques de sécurité courantes susceptibles d’affecter son infrastructure et les communications.
  
## <a name="compromised-key-attack"></a>Attaque par clé compromise

Une clé est un code ou un nombre secret utilisé pour chiffrer, déchiffrer ou valider des informations confidentielles. Il existe deux clés critiques en cours d’utilisation dans une infrastructure à clé publique (PKI) qui doit être pris en compte : 
  
- la clé privée que possède chaque détenteur de certificat ;
    
- la clé de session, utilisée après l’identification et l’échange de clé de session entre les partenaires communiquant entre eux.
    
Une attaque par clé compromise se produit lorsqu’un intrus parvient à identifier la clé privée ou la clé de session. Lorsque l’intrus parvient à déterminer la clé, il s’en sert pour déchiffrer des données chiffrées, à l’insu de l’expéditeur des données.
  
Skype pour Business Server utilise les fonctionnalités de l’infrastructure à clé publique dans le système d’exploitation Windows Server pour protéger les données de clé utilisées pour le chiffrement des connexions Transport Layer Security (TLS). Les clés utilisées pour le chiffrement multimédia sont échangées via des connexions TLS.
  
## <a name="network-denial-of-service-attack"></a>Attaque réseau par déni de service

Une attaque par déni de service se produit lorsqu’une personne malveillante empêche des utilisateurs valides de travailler et d’utiliser le réseau normalement. Pour ce faire, elle inonde le service avec des demandes légitimes qui submergent l’utilisation du service par les utilisateurs légitimes. Lors d’une attaque de ce type, la personne malveillante peut :
  
- envoyer des données non valides à des applications et des services exécutés sur le réseau faisant l’objet de l’attaque, afin de perturber leur exécution normale ;
    
- envoyer un volume de trafic important, de manière à surcharger le système jusqu’à ce que celui-ci cesse de fonctionner ou nécessite beaucoup de temps pour répondre aux demandes légitimes ;
    
- masquer les signes d’attaque ;
    
- empêcher les utilisateurs d’accéder aux ressources réseau.
    
## <a name="eavesdropping-sniffing-snooping"></a>Attaque par écoute (Eavesdropping)

Une attaque par écoute peut se produire lorsqu’une personne malveillante parvient à accéder au chemin d’accès des données d’un réseau et qu’elle peut ainsi surveiller et lire le trafic. Cette attaque est également appelée reniflage (« sniffing ») ou surveillance (« snooping »). Si le trafic consiste en du texte simple, l’intrus peut lire le trafic lorsqu’il accède au chemin d’accès des données. Par exemple, une attaque peut être lancée en contrôlant un routeur sur le chemin de données. 
  
La recommandation par défaut et le paramètre pour le trafic dans Skype pour Business Server consiste à utiliser (Mutual TLS) entre serveurs approuvés et TLS à partir du client au serveur. Cette mesure de protection rend ce type d’attaque difficile, voire impossible, durant le laps de temps pendant lequel une conversation donnée peut être attaquée. Le protocole TLS authentifie toutes les parties et chiffre le trafic. Ceci n’empêche pas les attaques par écoute, mais l’intrus ne peut pas lire le trafic à moins que le chiffrement ne soit rompu.
  
Le protocole TURN (Traversal Using Relay NAT) n’exige pas que le trafic soit chiffré. Les informations acheminées sont protégées par l’intégrité des messages. Bien qu’elles puissent faire l’objet d’une attaque par écoute, les informations acheminées (autrement dit, les adresses IP et le port) peuvent être extraites directement, en observant simplement les adresses source et de destination des paquets. Le service Edge A/V s’assure que les données sont valides en vérifiant l’intégrité du message à l’aide d’une clé dérivée de plusieurs éléments, dont un mot de passe TURN, qui n’est jamais transmise en texte en clair. Si le protocole SRTP (Secure Real Time Protocol) est utilisé, le trafic multimédia est également chiffré.
  
## <a name="identity-spoofing-ip-address-and-caller-id-spoofing"></a>Usurpation d’identité (adresse IP et l’appelant usurpation d’Id)

Identité l’usurpation d’identité se produit lorsque l’intrus détermine utilise un numéro de téléphone d’un utilisateur valid (id de l’appelant) ou une adresse IP d’un réseau, un ordinateur ou un composant réseau sans être autorisé au pour faire. Une attaque permet à l’intrus peut opérer comme si l’intrus est l’entité habituellement identifiée par le numéro de téléphone (id de l’appelant) ou l’adresse IP.

Dans le contexte de Skype pour Business Server, usurpation d’adresse IP intervient uniquement si un administrateur a effectué les deux opérations suivantes :
  
- configuré des connexions qui prennent uniquement en charge le protocole TCP (Transmission Control Protocol), ce qui n’est pas recommandé car les communications TCP ne sont pas chiffrées ;
    
- marqué les adresses IP de ces connexions en tant qu’hôtes approuvés.
    
Ce problème est moins grave pour les connexions TLS (Transport Layer Security), car TLS authentifie toutes les parties et chiffre le trafic. L’utilisation du protocole TLS empêche une personne malveillante d’usurper une adresse IP sur une connexion spécifique (par exemple, les connexions Mutual TLS). Mais une personne malveillante peut usurper toujours l’adresse du serveur DNS qui utilise Skype pour Business Server. Toutefois, étant donné que l’authentification dans Skype pour les entreprises est effectuée avec des certificats, une personne malveillante aurait pas un certificat valide requis usurper une des parties de la communication.

En revanche, l’usurpation d’identité des Id d’appelant intervient lorsque vous avez établi une jonction SIP entre un fournisseur, passerelle PSTN ou un autre système PBX et Skype pour Business Server. Dans ces cas-là, Skype pour Business Server n’offre pas de protection à se prémunir contre l’usurpation des id d’appelant. Cela signifie qu’un Skype pour l’utilisateur d’entreprise peut recevoir un appel de la jonction SIP avec un id d’appelant usurpés affichant le numéro de téléphone ou le nom complet (si la recherche inversée de numéros s’applique) d’une autre Skype pour l’utilisateur d’entreprise. Protection à celle-ci doit être appliquée sur le côté fournisseur, passerelle PSTN ou PBX.
  
## <a name="man-in-the-middle-attack"></a>Attaque de l’intercepteur (« man-in-the-middle »)

Une attaque man-in-the-middle se produit lorsqu’une personne malveillante redirige les communications entre deux utilisateurs par le biais d’ordinateur son propre l’insu des deux utilisateurs communication. L’intrus peut surveiller et lire le trafic avant de l’acheminer vers le destinataire concerné. Chacun des utilisateurs envoie et reçoit du trafic vers/de l’intrus, alors qu’il pense communiquer avec l’utilisateur concerné uniquement. Cela peut se produire si une personne malveillante modifie les services de domaine Active Directory pour ajouter son serveur en tant que serveur approuvé, ou si elle modifie DNS (Domain Name System) pour faire en sorte que les clients se connectent au serveur via l’ordinateur de l’intrus à l’origine de l’attaque. Une attaque de l’intercepteur peut également affecter le trafic multimédia entre deux clients. Toutefois, dans Skype pour Business Server point à point audio, vidéo et partage d’application, les flux sont chiffrés avec SRTP, à l’aide des clés de chiffrement qui sont négociées entre homologues qui utilisent le protocole SIP (Session Initiation) sur TLS. Les serveurs tels que le serveur de conversation de groupe utilisent le protocole HTTPS pour sécuriser le trafic.
  
## <a name="rtp-replay-attack"></a>Attaque par relecture RTP

Une attaque par relecture se produit lorsqu’une transmission multimédia valide entre deux correspondants est interceptée, puis retransmise à des fins malveillantes. SRTP utilisé par le protocole de signalisation sécurisé protège les transmissions des attaques par relecture en activant le récepteur conserve un index de paquets RTP déjà reçus et la comparaison de chaque nouveau paquet avec ceux déjà répertoriés dans l’index.
  
## <a name="spim"></a>Messages instantanés indésirables (Spim)

Le spim correspond à des messages instantanés commerciaux ou des demandes d’abonnement aux informations de présence non sollicités. S’il ne constitue pas à lui seul une menace envers le réseau, il peut néanmoins perturber les activités des utilisateurs et avoir un impact négatif sur la disponibilité des ressources et la production. Il représente donc un risque potentiel pour le réseau. Prenons le cas d’utilisateurs qui génèrent du spim en s’envoyant mutuellement des demandes. Un utilisateur peut en bloquer un autre pour ne plus recevoir de messages instantanés indésirables. Toutefois, dans le cas de la fédération, il peut s’avérer difficile de faire face à une attaque de spim coordonnée, à moins de désactiver la fédération pour le partenaire.
  
## <a name="viruses-and-worms"></a>Virus et vers

Un virus est une unité de code ayant pour finalité la reproduction d’unités de code similaires supplémentaires. Pour fonctionner, un virus a besoin d’un hôte, par exemple un fichier, un e-mail ou un programme. Aworm est une unité de code dont la fonction consiste à reproduire d’unités de code supplémentaire, similaire, mais il n’est pas nécessaire à un hôte. Les virus et les vers apparaissent principalement lors des transferts de fichiers entre clients ou lorsque des URL sont envoyées par d’autres utilisateurs. Si vous avez un virus sur votre ordinateur, il peut, par exemple, utiliser votre identité et envoyer des messages instantanés en votre nom.
  
## <a name="personally-identifiable-information"></a>Informations d’identification personnelle

Skype pour Business Server a la possibilité de divulguer des informations sur un réseau public qui peut-être être en mesure d’être liés à une seule personne. Ces informations appartiennent à deux catégories :
  
- **Données de présence amélioré** Données de présence enrichie sont informations un utilisateur peut choisir de partager ou non sur un lien vers un partenaire fédéré ou avec des contacts au sein d’une organisation. Elles ne sont pas partagées avec les utilisateurs d’un réseau public de messagerie instantanée. Selon les stratégies de groupe en vigueur et la configuration du client, l’administrateur système peut contrôler ces informations. Dans Skype pour Business Server, le mode de confidentialité de la présence enrichie peut être configuré pour un utilisateur individuel empêcher Skype pour les utilisateurs professionnels pas sur la liste des Contacts de l’utilisateur de voir les informations de présence de l’utilisateur. Mode de confidentialité de la présence enrichie n’empêche pas les utilisateurs de Microsoft Office Communicator 2007 et Microsoft Office Communicator 2007 R2 ne peuvent pas voir les informations de présence d’un utilisateur. Pour plus d’informations sur le déploiement du client et présence, voir [déployer les clients pour Skype pour Business Server](../../deploy/deploy-clients/deploy-clients.md) et la [planification de la messagerie instantanée et présence dans Skype pour Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
    
- **Données obligatoires** Données obligatoires est requises pour le bon fonctionnement du serveur ou le client et ne sont pas sous le contrôle de l’administration du client ou le système. Il s’agit d’informations qui sont nécessaires au niveau du réseau ou serveur à des fins de routage, l’état de maintenance et de signalisation.
    
Les tableaux suivants répertorient les données exposées sur un réseau public.
  
**Données de présence enrichie**

|**Données divulguées**|**Paramètres possibles**|
|:-----|:-----|
|Données personnelles  <br/> |Nom, Fonction, Société, Adresse électronique, Fuseau horaire  <br/> |
|Numéros de téléphone  <br/> |Bureau, Mobile, Domicile  <br/> |
|Informations de calendrier  <br/> |Libre/Occupé(e), notification d’absence du bureau, détails de réunion (pour les personnes ayant accès à votre calendrier)  <br/> |
|Statut de présence  <br/> |Absent(e), Disponible, Occupé(e), Ne pas déranger, Hors connexion  <br/> |
   
**Données obligatoires**


| **Données divulguées** | **Exemples d’informations**                            |
|:-------------------|:---------------------------------------------------|
| Adresse IP  <br/>  | Adresse réelle de l’ordinateur ou adresse traduite via NAT  <br/> |
| URI SIP  <br/>     | jeremylos@litwareinc.com  <br/>                    |

