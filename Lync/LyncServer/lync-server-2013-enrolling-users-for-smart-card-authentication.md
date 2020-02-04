---
title: 'Lync Server 2013 : inscription des utilisateurs pour l’authentification par carte à puce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 750e77b342b48d2c81bf05e160779ca5566f5a2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a>Inscription des utilisateurs à l’authentification par carte à puce dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-03_

Deux méthodes permettent d’inscrire les utilisateurs pour l’authentification par carte à puce. La méthode la plus simple consiste à faire s’inscrire directement les utilisateurs pour l’authentification par carte à puce par l’inscription par le biais du web. La méthode la plus complexe implique d’utiliser un agent d’inscription. Cette rubrique décrit l’inscription automatique pour les certificats de carte à puce.

Pour plus d’informations sur l’inscription au nom des utilisateurs en tant qu’agent d’inscription, voir inscrire des certificats pour le compte d’autres utilisateurs [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367)à l’adresse.

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a>Inscription des utilisateurs pour l’authentification par carte à puce

1.  Connectez-vous à Windows 8 Workstation en utilisant les informations d’identification d’un utilisateur compatible Lync.

2.  Lancez Internet Explorer.

3.  Accédez à la page d’inscription sur le Web de l' **autorité** de https://MyCA.contoso.com/certsrv)certification (par exemple,.
    
    <div>
    

    > [!NOTE]  
    > Si vous utilisez Internet Explorer 10, vous devrez peut-être afficher ce site web en mode de compatibilité.

    
    </div>

4.  Dans la page **Bienvenue**, sélectionnez **Demander un certificat**.

5.  Sélectionnez ensuite **Demande avancée**.

6.  Sélectionnez **Créer et envoyer une demande de requête auprès de cette autorité de certification**.

7.  Sélectionnez **Utilisateur de carte à puce** sous la section **Modèle de certificat**, puis remplissez la demande de certificat avancée avec les valeurs suivantes :
    
      - Sous **Options des clés**, vérifiez que les paramètres suivants sont sélectionnés :
        
          - Sélectionnez la case d’option **Créer un jeu de clés**.
        
          - Dans **Fournisseur de services de chiffrement**, sélectionnez **Fournisseur de services de chiffrement Microsoft pour carte à puce**.
        
          - Dans **Utilisation de la clé**, sélectionnez **Exchange** (seule option disponible).
        
          - Dans **Taille de la clé**, entrez **2048**.
        
          - Vérifiez que l’option **Nom de conteneur de clé automatique** est sélectionnée.
        
          - Laissez les autres cases à cocher désactivées.
    
      - Sous **Options supplémentaires**, vérifiez que les valeurs suivantes sont sélectionnées :
        
          - Dans **Format de la demande**, sélectionnez **CMC**.
        
          - Dans **Algorithme de hachage**, sélectionnez **sha1**.
        
          - Dans **Nom convivial**, entrez **Smardcard Certificate**.

8.  Si vous utilisez un lecteur de cartes à puces physiques, insérez la carte à puce dans l’appareil.

9.  Cliquez sur **Envoyer** pour envoyer la demande de certificat.

10. Lorsque vous y êtes invité, entrez le code confidentiel utilisé pour créer la carte à puce virtuelle.
    
    <div>
    

    > [!NOTE]  
    > La valeur par défaut du code confidentiel de la carte à puce virtuelle est « 12345678 ».

    
    </div>

11. Une fois le certificat émis, cliquez sur **Installer ce certificat** pour terminer la procédure d’inscription.
    
    <div>
    

    > [!NOTE]  
    > Si votre demande de certificat échoue avec l’erreur « Ce navigateur web ne prend pas en charge la génération des demandes de certificat », vous pouvez résoudre le problème de trois façons : 
    > <OL>
    > <LI>
    > <P>Activez l’affichage de compatibilité dans Internet Explorer.</P>
    > <LI>
    > <P>Activez l’option Activer les paramètres Intranet dans Internet Explorer.</P>
    > <LI>
    > <P>Sélectionnez le paramètre Rétablir toutes les zones au niveau par défaut sous l’onglet Sécurité du menu Options Internet Explorer.</P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

