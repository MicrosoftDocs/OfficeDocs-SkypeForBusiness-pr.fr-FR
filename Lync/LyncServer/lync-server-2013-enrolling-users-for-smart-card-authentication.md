---
title: Insciption des utilisateurs pour l’authentification par carte à puce
TOCTitle: Insciption des utilisateurs pour l’authentification par carte à puce
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn308570(v=OCS.15)
ms:contentKeyID: 56269637
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Insciption des utilisateurs pour l’authentification par carte à puce

 

_**Dernière rubrique modifiée :** 2016-12-08_

Deux méthodes permettent d’inscrire les utilisateurs pour l’authentification par carte à puce. La méthode la plus simple consiste à faire s’inscrire directement les utilisateurs pour l’authentification par carte à puce par l’inscription via le web, tandis que la méthode la plus complexe implique l’utilisation d’un agent d’inscription. Cette rubrique décrit l’inscription automatique pour les certificats de carte à puce.

Pour plus d’informations sur l’inscription des utilisateurs en leur nom via un agent d’inscription, voir la rubrique S’inscrire pour obtenir des certificats au nom d’autres utilisateurs à l’adresse [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).

## Inscrire des utilisateurs pour l’authentification par carte à puce

1.  Connectez-vous à la station de travail Windows 8 à l’aide des informations d’identification d’un utilisateur prenant en charge Lync.

2.  Lancez Internet Explorer.

3.  Accédez à la page d’**inscription de l’autorité de certification via le web** (par exemple, https://MyCA.contoso.com/certsrv).
    
    > [!NOTE]  
    > Si vous utilisez Internet Explorer 10, vous devrez peut être afficher ce site web en mode de compatibilité.

4.  Dans la page **Bienvenue**, sélectionnez **Demander un certificat**.

5.  Sélectionnez ensuite **Demande avancée**.

6.  Sélectionnez **Créer et soumettre une demande de requête auprès de cette autorité de certification**.

7.  Sélectionnez **Utilisateur de carte à puce** sous la section **Modèle de certificat**, puis complétez la demande de certificat avancée avec les valeurs suivantes :
    
      - Sous **Options des clés**, vérifiez que les paramètres suivants sont sélectionnés :
        
          - Sélectionnez la case d’option **Créer un nouveau jeu de clés**.
        
          - Pour **Fournisseur de services de chiffrement**, sélectionnez **Fournisseur de services de chiffrement Microsoft pour carte à puce**.
        
          - Pour **Utilisation de la clé**, sélectionnez **Exchange** (seule option disponible).
        
          - Pour **Taille de la clé**, entrez **2048**.
        
          - Vérifiez que l’option **Nom de conteneur de clé automatique** est sélectionnée.
        
          - Laissez les autres cases à cocher désactivées.
    
      - Sous **Options supplémentaires**, vérifiez que les valeurs suivantes sont sélectionnées :
        
          - Pour **Format de la demande**, sélectionnez **CMC**.
        
          - Pour **Algorithme de hachage**, sélectionnez **sha1**.
        
          - Pour **Nom convivial**, entrez **Certificat de carte à puce**.

8.  Si vous utilisez un lecteur de cartes à puces physiques, insérez la carte à puce dans l’appareil.

9.  Cliquez sur **Envoyer** pour envoyer la demande de certificat.

10. Lorsque vous y êtes invité, entrez le code confidentiel utilisé pour créer la carte à puce virtuelle.
    
    > [!NOTE]  
    > La valeur par défaut du code confidentiel de la carte à puce virtuelle est « 12345678 ».

11. Une fois le certificat émis, cliquez sur **Installer ce certificat** pour terminer le processus d’inscription.
    
> [!NOTE]  
> Si votre demande de certificat échoue avec l’erreur « Ce navigateur web ne prend pas en charge la génération des demandes de certificat », vous pouvez résoudre le problème de trois façons :
> <ol>
> <li><p>Activez l’affichage de compatibilité dans Internet Explorer.</p></li>    
> <li><p>Activez l’option Activer les paramètres Intranet dans Internet Explorer.</p></li>    
> <li><p>Sélectionnez le paramètre Rétablir toutes les zones au niveau par défaut sous l’onglet Sécurité du menu Options Internet Explorer.</p></li>
> </ol>