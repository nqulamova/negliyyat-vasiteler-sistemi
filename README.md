using System;
using System.Collections.Generic;

class Vehicle
{
    public string Brand;
    public int Speed;

    public Vehicle(string brand, int speed)
    {
        Brand = brand;
        Speed = speed;
    }

    public virtual void MakeSound()
    {
        Console.WriteLine("Neqliyyat vasitəsi ses cixarir.");
    }
}

class Car : Vehicle
{
    public Car(string brand, int speed)
        : base(brand, speed)
    {
    }

    public override void MakeSound()
    {
        Console.WriteLine(Brand + " masin: Bip-bip!");
    }
}

class Motorcycle : Vehicle
{
    public Motorcycle(string brand, int speed)
        : base(brand, speed)
    {
    }

    public override void MakeSound()
    {
        Console.WriteLine(Brand + " motosiklet: Vroom-vroom!");
    }
}

class Bicycle : Vehicle
{
    public Bicycle(string brand, int speed)
        : base(brand, speed)
    {
    }

    public override void MakeSound()
    {
        Console.WriteLine(Brand + " velosiped: Zeng!");
    }
}

class Program
{
    static void Main()
    {
        List<Vehicle> vehicles = new List<Vehicle>();

        vehicles.Add(new Car("BMW", 200));
        vehicles.Add(new Motorcycle("Honda", 150));
        vehicles.Add(new Bicycle("Scott", 30));

        foreach (Vehicle vehicle in vehicles)
        {
            vehicle.MakeSound();
        }
    }
}
